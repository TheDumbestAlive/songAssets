<html>
  <head>
    <script src="https://cdn.jsdelivr.net/processing.js/1.4.8/processing.min.js"></script> 
    <script src = "https://cdn.jsdelivr.net/gh/thedumbestalive/songAssets/LoopingThroughTheRooms.js"> </script>
  </head>
  
  <body id = 'body'>
    <canvas id = 'DAW'></canvas>
    <script>
    try{
        const audioCtx = new AudioContext();
let volume = 0.4;
let fadeTime = 1;
let instrument = 'square';
let masterVol = audioCtx.createGain();
masterVol.connect(audioCtx.destination);

let notes = ['a','a#','b','c','c#','d','d#','e','f','f#','g','g#'];
let BaseOctave = 1;

let baseHz = 55;
let SEMITONE_CONSTANT = 1.05946;
let TRANSPOSE = 0;

let Note  = function(note) /* => Number */ {
    let saveNote = note;
    note = String(note);
    note = note.toLowerCase();
    note = note.split('');
    let pitch = note.filter(function(x) {
        return notes.includes(x)
    })[0];
    let octave = note.filter(function(x){
        return [1,2,3,4,5,6,7,8,9].includes(Number(x))
    })[0];
    if(octave < BaseOctave || !octave){
        octave = BaseOctave;
    }
   
    octave -= BaseOctave;
    octave *= 12;
    pitch = notes.indexOf(pitch);
    if(pitch === -1){
        throw Error('Invalid pitch passed to Note. Did you mean to write ["+saveNote+"]?')
    }
    if(note.indexOf('#') !== -1){
        pitch++;
    }
    return pitch + octave + TRANSPOSE;
  
};


let oscs = {};
let playNote = function(note, duration, wave, nofade) /* => undefined */{
    if(audioCtx.state !== 'suspended'){
        let difference = Note(note);
        
        if(wave === 'saw'){
            wave = 'sawtooth';
        }
        let vol = audioCtx.createGain();
        let osc = audioCtx.createOscillator();
        if(!['sine', 'triangle', 'sawtooth', 'square'].includes(wave)){
            wave = 'sine';
        }
        if(!duration || duration < 0){
            return;
        }
        osc.type = wave;
        let totalSemitoneJump = Math.pow(SEMITONE_CONSTANT, difference);
      
        osc.frequency.value = baseHz * totalSemitoneJump;
        let oscId = String(osc.frequency.value) + wave;
                if(oscs[oscId]){
            oscs[oscId].stop(0);
                console.log('Note Dropped.');
            delete oscs[oscId];
        }
    
        oscs[oscId] = osc;
        oscs[oscId].FREQUENCY_DIFFERENCE = difference;
        
        vol.gain.value = volume;
        if(!nofade){
        vol.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + duration);
        }
        
        osc.connect(vol);
        vol.connect(masterVol);
        osc.start();
        osc.stop(audioCtx.currentTime + duration);
        osc.addEventListener('ended', function(){
            delete oscs[oscId];
        });
    }
    else{
        console.warn('Failed to play audio. AudioContext must be started after a user interaction.');
    }
};
      
      let selectedTrack = 2;
let tracks = [];
let masterSheet = [];
let lyricStep = 0;
let body = document.getElementById('body')
for(let i = 0; i < json.tracks.length; i++){
    let currTrack = json.tracks[i];
    tracks.push([])
    for(let k = 0; k < currTrack.notes.length; k++){
        tracks[i].push({
            note: currTrack.notes[k].name,
            time: currTrack.notes[k].time,
            duration: currTrack.notes[k].duration,
        })
        masterSheet.push({
            note: currTrack.notes[k].name,
            time: currTrack.notes[k].time,
            duration: currTrack.notes[k].duration,
        })
    }
}
      
    let getOctave = function (octave) {
    return notes.map(function(x){
        return x + String(octave)
    })
}
    let getNote = function (note, maxLength)  {
        let indx = 0;
        let found = [];
        while(found.length < maxLength && indx < tracks[selectedTrack].length){
            if (tracks[selectedTrack][indx].note.toLowerCase() === note.toLowerCase()) {
              found.push(tracks[selectedTrack][indx])
            }
          indx++;
        }
      return found;
    }
    let currOctave = 4;
    let processing = function (p) {
            p.setup = function() {
                p.width = window.innerWidth;
                p.height = window.innerHeight;
                p.background(255,255,255);
                console.log(tracks.length + ' tracks');
            }

            p.draw = function() {
                /*
              for(let i = 0; i < masterSheet.length; i++){

                    let currNote = masterSheet[i];
                    if(audioCtx.currentTime > currNote.time){
                        playNote(currNote.note, currNote.duration + 1, instrument)
                        masterSheet.splice(i,1)
                        p.background(Math.random() * 255, Math.random() * 255, Math.random() * 255)
                    }
                
              }
              */
              if(audioCtx.state !== 'suspended'){
                  p.background(255,255,255);
              for(let i = 0; i < tracks.length; i++){
                  for(let k = 0; k < tracks[i].length; k++){
                      let currNote = tracks[i][k]
                      if(audioCtx.currentTime > currNote.time){
                        playNote(currNote.note, currNote.duration + 1, instrument)
                        tracks[i].splice(k,1)
                        if(i === 0){
                        lyricStep++;
                        }
                    }
                      
                  }
              }
              for(let i = 0; i < tracks.length; i++){
                  
              }
              }
              else{
                  p.background(255,255,255);
                  p.fill(0,0,0)
                  p.text('Please click the screen.', p.width / 2 - p.textWidth('Please click the screen.') / 2, p.height / 2)
              }
            }
            
            p.mouseClicked = function(){
                if(audioCtx.state === 'suspended'){
                    audioCtx.resume();
                }
                if(p.mouseButton === 39){
                    audioCtx.suspend();
                }
            }
            
            

      };
      let canvas = document.getElementById('DAW');
      canvas.style.position = 'absolute';
      canvas.style.left = 0 + 'px';
      canvas.style.top = 0 + 'px';
      let pjs = new Processing(canvas, processing);
    }
    catch (e)
    {
        console.log('Error: '+e)
    }
    </script>
  </body>
</html>
