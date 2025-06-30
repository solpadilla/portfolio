<template>
  <div class="dark">
    <div class="transition-main">
      <main>
        <section class="h-screen w-screen m-0 max-w-none">
          <div id="map" class="w-full h-full"></div>
        </section>
      </main>
    </div>
  </div>
</template>

<style>
body {
  overflow: hidden;
}
</style>

<script setup>
const googleKey = "AIzaSyCsXSFEGbAa_b5MW7xXvGBA97vcv8l1U_c"
const marketScan = {"range":7.9,"is_nightly":true,"auto_label":"10 within 7.9 km, 20 within 97.9 km","sort":{"key":"","direction":"asc"},"filters":{"bedroom_min":1,"bedroom_max":2,"pets_ok":true},"prices":{"low":{"amount":40,"count":4,"percentage":40},"fair":{"amount":70,"count":7,"percentage":70},"high":{"amount":100,"count":10,"percentage":100}},"nb_properties":10,"nb_accepted":10,"bedrooms":1,"longitude":-123.1166892,"latitude":49.28822479999999,"properties":[{"id":"29321317744","price":10,"price_per_night":10,"price_per_month":300,"distance":1.1,"bedrooms":"1.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"low","property_url":"https://www.airbnb.com/rooms/844402747869472882","address":"933 Seymour Street, Vancouver, BC V6B 6L6","longitude":"-123.1214878","latitude":"49.279212"},{"id":"29319497327","price":20,"price_per_night":20,"price_per_month":600,"distance":5.7,"bedrooms":"2.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"low","property_url":"https://www.airbnb.com/rooms/1211665126203841889","address":"2843 East 5th Avenue, Vancouver, BC V5M 1N4","longitude":"-123.0459788","latitude":"49.26595409999999"},{"id":"29322401370","price":30,"price_per_night":30,"price_per_month":900,"distance":7.9,"bedrooms":"2.0","bathrooms":"2.0","pets_ok":"true","accepted":true,"range":"low","property_url":"https://www.airbnb.com/rooms/45241913","address":"335 Southborough Drive, West Vancouver, BC V7S 1L9","longitude":"-123.1241654","latitude":"49.3586676"},{"id":"29312653056","price":40,"price_per_night":40,"price_per_month":1200,"distance":5.8,"bedrooms":"1.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"low","property_url":"https://www.airbnb.com/rooms/783449724931059319","address":"2096 East 23rd Avenue, Vancouver, BC V5N 2V1","longitude":"-123.0628087","latitude":"49.2491979"},{"id":"29316967801","price":50,"price_per_night":50,"price_per_month":1500,"distance":3.1,"bedrooms":"2.0","bathrooms":"2.0","pets_ok":"true","accepted":true,"range":"fair","property_url":"https://www.airbnb.com/rooms/24066686","address":"2777 Oak Street, Vancouver, BC V6H 3N3","longitude":"-123.1271885","latitude":"49.2608608"},{"id":"29322090796","price":60,"price_per_night":60,"price_per_month":1800,"distance":0.9,"bedrooms":"2.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"fair","property_url":"https://corporatestays.com/en/cs-buildings/telus-garden/","address":"777 Richards Street, Vancouver, BC V6B 0M6","longitude":"-123.117572","latitude":"49.2805943"},{"id":"29324115080","price":70,"price_per_night":70,"price_per_month":2100,"distance":4.2,"bedrooms":"1.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"fair","property_url":"https://www.airbnb.com/rooms/1297998576839507129","address":"1440 East Broadway, Vancouver, BC V5N 5P2","longitude":"-123.0754315","latitude":"49.2621707"},{"id":"29319497336","price":80,"price_per_night":80,"price_per_month":2400,"distance":6.8,"bedrooms":"1.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"high","property_url":"https://www.airbnb.com/rooms/1151575752840002031","address":"333 Boundary Road, Vancouver, BC V5K 1Y6","longitude":"-123.023875","latitude":"49.2818301"},{"id":"29327979294","price":90,"price_per_night":90,"price_per_month":2700,"distance":1.2,"bedrooms":"2.0","bathrooms":"2.0","pets_ok":"true","accepted":true,"range":"high","property_url":"https://www.airbnb.com/rooms/53151153","address":"2202-689 Abbott Street, Vancouver, BC V6B 0J2","longitude":"-123.1079385","latitude":"49.2788861"},{"id":"29329341193","price":100,"price_per_night":100,"price_per_month":3000,"distance":7.9,"bedrooms":"2.0","bathrooms":"1.0","pets_ok":"true","accepted":true,"range":"high","property_url":"https://www.airbnb.com/rooms/buHdsCMp","address":"477 West 59th Avenue, Vancouver, BC V5X 1X4","longitude":"-123.1156798","latitude":"49.2171422"}]}

// Google Maps initialization
onMounted(() => {
  // Load Google Maps API
  const script = document.createElement('script')
  script.src = `https://maps.googleapis.com/maps/api/js?key=${googleKey}&callback=initMap&libraries=marker`
  script.async = true
  script.defer = true
  document.head.appendChild(script)
  
  // Initialize map when API is loaded
  window.initMap = () => {
    // Default location (you can change these coordinates)
    const location = { lat: 49.28822479999999, lng: -123.1166892 }
    
    const map = new google.maps.Map(document.getElementById('map'), {
      zoom: 13,
      center: location,
      mapTypeId: 'roadmap'
    })

    // Draw the range circle (radius in meters)
    new google.maps.Circle({
      strokeColor: "#347cf7",
      strokeOpacity: 0.6,
      strokeWeight: 2,
      fillColor: "#347cf7",
      fillOpacity: 0.05,
      map,
      center: location,
      radius: 83.1 * 1000 // 83.1 km in meters
    })

    const marker = new google.maps.Marker({
      position: location,
      map: map,
      title: 'Home',
    })

    // Variable to keep track of the currently open InfoWindow
    let openInfoWindow = null;
    // Close any open InfoWindow when clicking on the map
    map.addListener('click', () => {
      console.log('Map clicked, closing infoWindow')
      // if (openInfoWindow) {
      //   openInfoWindow.close();
      //   openInfoWindow = null;
      // }
    });

    // Loop through properties and add markers (add lat/lng to your properties as needed)
    marketScan.properties.forEach(property => {
      // Example: add lat/lng manually for demo (replace with real data if available)
      // property.lat = ...; property.lng = ...;
      console.log(`Adding marker for property: ${property.property_url}`)
      if (property.latitude && property.longitude) {
        const propertyMarker = new google.maps.Marker({
          position: { lat: parseFloat(property.latitude), lng: parseFloat(property.longitude) },
          map: map,
          title: property.property_url,
          icon: {
            url: 'data:image/svg+xml;utf-8,<svg width="24" height="36" viewBox="0 0 24 36" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 0C5.372 0 0 5.372 0 12c0 7.732 10.5 22.5 11.25 23.625a1.5 1.5 0 0 0 2.5 0C13.5 34.5 24 19.732 24 12c0-6.628-5.372-12-12-12zm0 18a6 6 0 1 1 0-12 6 6 0 0 1 0 12z" fill="%23347cf7"/></svg>',
            scaledSize: new google.maps.Size(24, 36)
          }
        })

        const infoWindow = new google.maps.InfoWindow({
          headerContent: `Property Details`,
          content: `
            <div class="font-sans">
              <div><b class="font-bold">Address:</b> ${property.address}</div>
              <div><b class="font-bold">Price:</b> ${property.price ? `$${property.price}` : 'N/A'}</div>
              <div><b class="font-bold">Range:</b> ${getRangeTag(property.range)}</div>

              <div class="mt-4">
                <div><b class="font-bold">Bedroom(s):</b> ${parseInt(property.bedrooms)}</div>
                <div><b class="font-bold">Bathroom(s):</b> ${parseInt(property.bathrooms)}</div>
                <div><b class="font-bold">Pets Allowed:</b> ${property.pets_ok === 'true' ? 'Pets Ok' : 'No Pets'}</div>
              </div>

              <div class="mt-4 flex justify-end"><a href="${property.property_url}" target="_blank" class="text-blue-500 hover:underline">View Property</a></div>
            </div>
          `,
        })

        propertyMarker.addListener('click', () => {
          if (openInfoWindow) openInfoWindow.close();
          infoWindow.open(map, propertyMarker);
          openInfoWindow = infoWindow;
        })
      }
    })
  }
})

// ...inside your forEach...
const getRangeTag = (range) => {
  if (range === 'low') {
    return `<span class="inline-block px-2 py-0.5 rounded text-xs font-semibold bg-green-100 text-green-700 border border-green-300">Low</span>`;
  }
  if (range === 'fair') {
    return `<span class="inline-block px-2 py-0.5 rounded text-xs font-semibold bg-yellow-100 text-yellow-700 border border-yellow-300">Fair</span>`;
  }
  if (range === 'high') {
    return `<span class="inline-block px-2 py-0.5 rounded text-xs font-semibold bg-red-100 text-red-700 border border-red-300">High</span>`;
  }
  return 'N/A';
};
</script>