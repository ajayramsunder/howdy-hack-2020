<template>
  <div id="map" ref="newmap"></div>
</template>

<script>
<<<<<<< HEAD
export default {
    data () {
        return {
=======
import mojson from '@/JSONs/money.json'
export default {
    data () {
        return {
            mJson: mojson,
            markers: [],
            loc1: false,
            loc2: false,
            loc3: false,
            loc4: false,
            loc5: false 
>>>>>>> f57c60cf3d341f1929fc56b8812692cd791318bb
        }
    },
    mounted () {
        this.createMap()
<<<<<<< HEAD
=======
        console.log(this.mJson.first_location)
        this.addMarker({lat: 30.615196,lng: -96.335957})
        //eslint-disable-next-line
        this.infoWindow = new google.maps.InfoWindow({})
        this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>The Commons</b></h> <p>Private Detective Han arrives at the Commons. He has been hired by Michael K. Young to investigate the disappearance of the number one football rookie in the state on the day of the Bama game, Shmoney Manziel. He is informed by university authorities that Manziel was last publicly sighted near the 12th Man Statue in Kyle Field and hastens to get a lead on the case.Each scene from now will contain an encryption that must be decrypted to find the next location (all misspellings are intentional) </p>")
>>>>>>> f57c60cf3d341f1929fc56b8812692cd791318bb
        // eslint-disable-next-line
        google.maps.event.addDomListener(this.map, 'click', (event) =>{
            this.addClickMarker(event.latLng)
        })
<<<<<<< HEAD
        // eslint-disable-next-line
        this.infowindow = new google.maps.InfoWindow()
=======
        
        
        

        
        
        
>>>>>>> f57c60cf3d341f1929fc56b8812692cd791318bb
    }, 
    methods: {
        createMap () {
            // eslint-disable-next-line
            this.map = new google.maps.Map( 
                this.$refs.newmap, { zoom: 8, center: {lat: 30.615196,lng: -96.335957}})
        },

        bindInfoWindow (marker, map, infoWindow, description) {
        marker.addListener('click', function () {
            infoWindow.setContent(description)
            infoWindow.open(map, marker)
        })
        },

        /*openInfoWindow(){
            // eslint-disable-next-line
            this.infoWindow = new google.maps.InfoWindow({
                content: "Hello Han"

            })

        },*/
        addMarker(latlng){
            // eslint-disable-next-line
            this.marker = new google.maps.Marker({
                position: latlng,
                map: this.map,
                title: "Click for your clue"
            })        
            this.markers.push(this.marker)
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
<<<<<<< HEAD
        bindInfoWindow (marker, map, infowindow, description) {
            marker.addListener('click', function () {
                infowindow.setContent(description)
                infowindow.open(map, marker)
            })
        },
=======

>>>>>>> f57c60cf3d341f1929fc56b8812692cd791318bb
    }  
}
</script>

<style>
#map{
    height: 400px;
    width: 75%  ;
    float: right
  }
</style>