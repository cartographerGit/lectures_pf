<div style="perspective: 1000px; width: 300px; height: 200px; display: inline-block;">
  <div style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;" 
       onmouseover="this.style.transform='rotateY(180deg)'" 
       onmouseout="this.style.transform='rotateY(0deg)'">
    
    <!-- FRONT SIDE -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #eee; display: flex; align-items: center; justify-content: center; border: 1px solid #ccc; border-radius: 10px;">
      <b>Question?</b>
    </div>

    <!-- BACK SIDE -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 10px;">
      <b>Answer!</b>
    </div>
  </div>
</div>
