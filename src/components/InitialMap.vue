<template>
  <div id="map" ref="newmap"></div>
</template>

<script>
import json from '@/JSONs/money.json'
export default {
    data () {
        return {
            dummy: NaN,
            dummy_object: {lat: 30, lng: 40},
            myJson: json
        }
    },
    mounted () {
        this.createMap()
        console.log(this.myJson.first_location)
        // eslint-disable-next-line
        google.maps.event.addDomListener(this.map, 'click', (event) =>{
            this.addClickMarker(event.latLng)
        })
    }, 
    methods: {
        createMap () {
            // eslint-disable-next-line
            this.map = new google.maps.Map( 
                this.$refs.newmap, { zoom: 8, center: {lat: 30.615196,lng: -96.335957}})
        },
        addClickMarker (latlng) {
            // if (this.mapType === 'markerPolyline') {
            // eslint-disable-next-line
            this.new_marker = new google.maps.Marker({position: latlng, map: this.map})
            this.places.push(this.new_marker.getPosition())
            this.markers.push(this.new_marker)
            this.currentPlace = null
            // }
    },

    }  
}
</script>

<style>
#map{
    height: 400px;
    width: 75%  ;
  }
</style>