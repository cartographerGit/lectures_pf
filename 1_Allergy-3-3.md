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


<div style="perspective: 1000px; width: 300px; height: 200px; display: inline-block; user-select: none;">
  <div onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
       style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;">
    
    <!-- ЛИЦЕВАЯ СТОРОНА -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #f9f9f9; display: flex; align-items: center; justify-content: center; border: 2px solid #3498db; border-radius: 12px; box-shadow: 2px 2px 10px rgba(0,0,0,0.1); font-family: sans-serif;">
      <b style="font-size: 1.2rem;">Вопрос?</b>
    </div>

    <!-- ОБРАТНАЯ СТОРОНА -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 12px; font-family: sans-serif;">
      <b style="font-size: 1.2rem;">Ответ!</b>
    </div>

  </div>
</div>
