<!-- ТЕКСТ НАВЕРХУ СТРАНИЦЫ -->
<div style="font-family: sans-serif; padding: 20px; line-height: 1.6; color: #333;">
  <p style="font-size: 1.1rem; color: #1b1b1b;">
   👆 Нажимайте на карточку, чтобы увидеть ответ <br><br>  
  🧠 Если вопрос вызвал затруднение, нажмите на кнопку «для повторения» под карточкой <br> <br>
    📖 Список затруднительных вопросов появится в самом низу страницы<br> <br>  
    📸 Можно заскринить его
  </p>
</div>


<style>
  /* Вынес общие стили в блок для чистоты кода */
  .card-container { width: 100%; margin-bottom: 40px; font-family: sans-serif; }
  .flip-card { perspective: 1000px; width: 100%; height: 30vh; min-height: 180px; user-select: none; margin-bottom: 10px; }
  .flip-inner { position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer; }
  .side { position: absolute; width: 100%; height: 100%; backface-visibility: hidden; display: flex; align-items: center; justify-content: center; border-radius: 15px; padding: 20px; box-sizing: border-box; text-align: center; font-size: 1.2rem; border: 2px solid #938AD7; }
  .back { background: #3498db; color: white; transform: rotateY(180deg); }
  .front { background: #fff; }
  .add-btn { width: 100%; padding: 18px; border: none; border-radius: 12px; background: #7cd4b5; color: white; cursor: pointer; font-weight: bold; font-size: 1rem; transition: 0.3s; }
</style>

<!-- КАРТОЧКА №1 -->
<div class="card-container">
  <div class="flip-card">
    <div class="flip-inner" onclick="flip(this)">
      <div class="side front">
        <b id="q1">Как переводится "Apple"?</b>
      </div>
      <div class="side back">Яблоко</div>
    </div>
  </div>
  <button class="add-btn" onclick="addToEnd('q1', this)">ДЛЯ ПОВТОРЕНИЯ</button>
</div>

<!-- КАРТОЧКА №2 -->
<div class="card-container">
  <div class="flip-card">
    <div class="flip-inner" onclick="flip(this)">
      <div class="side front">
        <b id="q2">Как переводится "Orange"?</b>
      </div>
      <div class="side back">Апельсин</div>
    </div>
  </div>
  <button class="add-btn" onclick="addToEnd('q2', this)">ДЛЯ ПОВТОРЕНИЯ</button>
</div>

<!-- КАРТОЧКА №3 -->
<div class="card-container">
  <div class="flip-card">
    <div class="flip-inner" onclick="flip(this)">
      <div class="side front">
        <b id="q3">Как переводится "Bread"?</b>
      </div>
      <div class="side back">Хлеб</div>
    </div>
  </div>
  <button class="add-btn" onclick="addToEnd('q3', this)">ДЛЯ ПОВТОРЕНИЯ</button>
</div>

<!-- ИТОГОВЫЙ СПИСОК -->
<div style="margin-top: 50px; padding: 20px; font-family: sans-serif; border-top: 3px solid #3498db; background: #f0f7ff;">
  <h3>Выбранные вопросы для изучения:</h3>
  <ul id="selected-list" style="font-size: 1.1rem; line-height: 2;"></ul>
</div>









<script>
// Функция переворота
function flip(cardInner) {
  cardInner.style.transform = (cardInner.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)');
}

// Функция добавления в список
function addToEnd(questionId, btn) {
  const text = document.getElementById(questionId).innerText;
  const list = document.getElementById('selected-list');
  
  // Проверка на дубликаты
  const exists = Array.from(list.children).some(li => li.innerText === text);
  
  if (!exists) {
    const li = document.createElement('li');
    li.innerText = text;
    list.appendChild(li);
    
    // Визуальный эффект успеха
    const originalText = btn.innerText;
    btn.innerText = "ДОБАВЛЕНО ✓";
    btn.style.background = "#7cd4b5";
    setTimeout(() => { 
      btn.innerText = originalText; 
      btn.style.background = "#7cd4b5"; 
    }, 800);
  } else {
    // Если уже есть в списке
    btn.innerText = "УЖЕ В СПИСКЕ";
    btn.style.background = "#938AD7";
    setTimeout(() => { btn.innerText = "ДОБАВИТЬ В СПИСОК"; btn.style.background = "#938AD7"; }, 800);
  }
}
</script>
