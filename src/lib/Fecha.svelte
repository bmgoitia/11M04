
<script>
    import {tweened} from "svelte/motion";
    import {cubicOut, backIn} from "svelte/easing";
  

    export let lv_day = 0;
    export let lv_month;
    export let lv_year; 
  
    const dValue = tweened(lv_day,{    
      duration: 1500,
      delay: 0,
      easing: cubicOut
    });

    

    const yValue = tweened(lv_year,{    
      duration: 1500,
      delay: 0,
      easing: cubicOut
      
    });

  
  
    const updValue = function(){
      dValue.set(lv_day);
     
      yValue.set(lv_year);
     
    }
  
    $: lv_day, updValue();  
   
    $: lv_year, updValue(); 
    
  
  
  </script>
  
  <p>
    <span>{Math.round($dValue)}</span>
    
    <span>{lv_month}</span>
    
    <span>{Math.round($yValue)}</span>
  </p>

  <style>
    

  </style>