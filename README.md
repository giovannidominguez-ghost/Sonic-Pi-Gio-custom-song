# Sonic-Pi-Gio-custom-song

use_bpm 128
use_synth :prophet

live_loop :chords do
  with_fx :reverb, mix: 0.6, room: 0.9 do
    
    # ---- SLOW INTRO (8 beats per chord) ----
    2.times do
      play_chord chord(:fs3, :minor), sustain: 7, release: 1
      sleep 8
      
      play_chord chord(:d3, :major), sustain: 7, release: 1
      sleep 8
      
      play_chord chord(:a2, :major), sustain: 7, release: 1
      sleep 8
      
      play_chord chord(:e3, :major), sustain: 7, release: 1
      sleep 8
    end
    
    # ---- BUILD SECTION (4 beats per chord) ----
    2.times do
      play_chord chord(:fs3, :minor), sustain: 3.5
      sleep 4
      
      play_chord chord(:d3, :major), sustain: 3.5
      sleep 4
      
      play_chord chord(:a2, :major), sustain: 3.5
      sleep 4
      
      play_chord chord(:e3, :major), sustain: 3.5
      sleep 4
    end
    
    # ---- DROP FEEL (2 beats per chord) ----
    loop do
      play_chord chord(:fs3, :minor), sustain: 1.5
      sleep 2
      
      play_chord chord(:d3, :major), sustain: 1.5
      sleep 2
      
      play_chord chord(:a2, :major), sustain: 1.5
      sleep 2
      
      play_chord chord(:e3, :major), sustain: 1.5
      sleep 2
    end
    
  end
end

sleep 64

live_loop :clap do
  6.times do
    sleep 1
    sample :perc_snap, amp: 1
    sleep 1
  end
  stop
end

sleep 18

live_loop :kick do
  6.times do
    with_fx :distortion, distort: 0.3 do
      sample :bd_tek, amp: 2.5
      sleep 1
    end
  end
  stop
end

piano_cat = "C:/Users/giovanni_dominguez/Downloads/Keyboard Cat - THE ORIGINAL.mp3"
sample piano_cat
