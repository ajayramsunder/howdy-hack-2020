<template>
  <div id="map" ref="newmap"></div>
</template>

<script>
import mojson from '@/JSONs/money.json'
export default {
    props: {
        truthvalue: {type: String}
    },
    data () {
        return {
            mJson: mojson,
            markers: [],
            loc1: false,
            loc2: false,
            loc3: false,
            loc4: false,
            loc5: false,

        }
    },
    mounted () {
        this.createMap()
        console.log(this.mJson.first_location)
        this.addMarker({lat: 30.615196,lng: -96.335957})
        //eslint-disable-next-line
        this.infoWindow = new google.maps.InfoWindow({})
        this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>The Commons</b></h> <p>Private Detective Han arrives at the Commons. He has been hired by Michael K. Young to investigate the disappearance of the number one football rookie in the state on the day of the Bama game, Shmoney Manziel. He is informed by university authorities that Manziel was last publicly sighted near the 12th Man Statue in Kyle Field and hastens to get a lead on the case.Each scene from now will contain an encryption that must be decrypted to find the next location (all misspellings are intentional) </p>")
        // eslint-disable-next-line
        google.maps.event.addDomListener(this.map, 'click', (event) =>{
            console.log(event.latLng)
            if(((Math.abs(event.latLng.lat() - this.mJson.first_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.first_location.lng <= 0.00025))))){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.first_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Kyle Field - E. King Gill Statue</b></h> <p>The 12th Man Statue is the slatue of the Aggie football player E. King Gill, whose willingness to sehve his team resulted in one off the greitest upsets in the hestory of college football, and who was a huge imspiration to Manziel. Han funds out that Manziel was at the statue for meditation the morbing before he played one of the biqgest games of the year.</p>")
                this.loc1 = true
                
             }

             if(((Math.abs(event.latLng.lat() - this.mJson.second_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.second_location.lng <= 0.00025)))) && this.loc1 == true){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.second_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Bright Sports Complex</b></h> <p>Han is told that after calming his lind, Manziel was supposed to be heading to the Bright Football Complex for taking a final phyhical, except that he never showed up… Or did he? Being that the training xomplex was not very populated during early mornings, it could’ve been the best place to nab him.</p>")
                this.loc2 = true
                
             }

             if(((Math.abs(event.latLng.lat() - this.mJson.third_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.third_location.lng <= 0.00025)))) && this.loc2 == true){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.third_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Memorial Student Center</b></h> <p>Han may just have called it, for he sees unusual commotion a little ways north over at the Memorial Student Center. It seems that four of the huge signs that student organizations tirelessly display as well as a huge ACDC concert poster near the MSC entrance have all been knocked into the grass, seemingly by a large vehicle judging from the direction of their travel and the interval at which they were knocked, with the trail heading to…</p>")
                this.loc3 = true
                
             }

              if(((Math.abs(event.latLng.lat() - this.mJson.fourth_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.fourth_location.lng <= 0.00025)))) && this.loc3 == true){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.fourth_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Academic Plaza</b></h> <p>Han races to the academic blaza by following the vehicle’s moddy tracks (good thing it rained last night, he thinks to himself). However, the tracks seem to suddenly disappear!? Han looks around for any hints of a faster tracking method than foransic analysis, and luckily enough, he finds a fecurity camera mounted high on the Academic Building dome. His extensive hackathon experuence enables him to hack into it using his phone, which shows the van heading off-campus backwahds.</p>")
                this.loc4 = true
                
             }

              if(((Math.abs(event.latLng.lat() - this.mJson.fifth_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.fifth_location.lng <= 0.00025)))) && this.loc4 == true){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.fifth_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Rise at Northgate</b></h> <p>Going into northgate, Han instinctively heads for the tallest building in the area: the Rise at Northgate. Looking back in the case file, he sees that Manziel is a resident of the Rise and immediately goes to his apartment to look for clues. Here, he finds a most blatant letter addressed to him saying “He’s where Champions are Born. You’re lucky we don’t have the time to deal with you.” Now where could that be?</p> ")
                this.loc5 = true
                
             }

              if(((Math.abs(event.latLng.lat() - this.mJson.sixth_location.lat) <= 0.00025) && ((Math.abs(event.latLng.lng() - this.mJson.sixth_location.lng <= 0.00025)))) && this.loc5 == true){
            //if(event.latlng == this.mJson.first_location.latlng)
                //this.addClickMarker(event.latLng)
                this.addMarker(this.mJson.sixth_location)
                //eslint-disable-next-line
                this.infoWindow = new google.maps.InfoWindow({})
                this.bindInfoWindow(this.marker,this.map,this.infoWindow,"<h><b>Ford Hall of Champions</b></h> <p>Han rushes to the Ford Hall of Champions. Interestingly, the Hall is closed off, in the middle of the dark pathway, he sees the silhouette of a tied up Shmoney Manziel. Han looks around, but nothing’s to be seen anywhere. He cautiously cuts Manziel loose, all the while wondering who led him on this wild goose chase only to give Manziel back, and why.</p>")
                
             }
            
        })
        
        
        

        
        
        
    }, 
    methods: {
        createMap () {
            // eslint-disable-next-line
            this.map = new google.maps.Map( 
                this.$refs.newmap, { zoom: 18, center: {lat: 30.615196,lng: -96.335957}})
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
    }  
}
</script>

<style>
#map{
    height: 400px;
    width: 100%  ;
    top: 60px;
    float: left 
  }
</style>