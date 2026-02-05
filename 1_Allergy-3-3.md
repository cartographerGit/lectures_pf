<div style="width: 100%; margin-bottom: 30px; box-sizing: border-box; font-family: sans-serif;">
  
  <!-- КАРТОЧКА: 100% ширины экрана -->
  <div style="perspective: 1000px; width: 100%; height: 40vh; min-height: 200px; user-select: none; margin-bottom: 10px;">
    <div id="card1" onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
         style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;">
      
      <!-- Лицевая сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #fff; display: flex; align-items: center; justify-content: center; border: 2px solid #3498db; border-radius: 12px; box-sizing: border-box; padding: 20px; text-align: center;">
        <h2 id="q1">Ваш вопрос здесь?</h2>
      </div>

      <!-- Обратная сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 12px; box-sizing: border-box; padding: 20px; text-align: center;">
        <h2>Правильный ответ</h2>
      </div>
    </div>
  </div>

  <!-- КНОПКА: Ниже карточки, тоже во всю ширину -->
  <button onclick="addToEnd('q1', this)" style="width: 100%; padding: 20px; border: none; border-radius: 12px; background: #2ecc71; color: white; cursor: pointer; font-weight: bold; font-size: 1.1rem; transition: background 0.3s;">
    ДОБАВИТЬ В СПИСОК
  </button>
</div>

<!-- СПИСОК В КОНЦЕ СТРАНИЦЫ -->
<div style="margin-top: 50px; padding: 20px; font-family: sans-serif; border-top: 2px solid #eee;">
  <h3>Вопросы, которые следует повторить<br>(сделать скрин):</h3>
  <ul id="selected-list"></ul>
</div>

<script>
function addToEnd(questionId, btn) {
  const text = document.getElementById(questionId).innerText;
  const list = document.getElementById('selected-list');
  
  // Проверка на дубликаты
  const exists = Array.from(list.children).some(li => li.innerText === text);
  if(exists) return;

  const li = document.createElement('li');
  li.innerText = text;
  li.style.margin = "10px 0";
  list.appendChild(li);

  // Эффект нажатия
  btn.style.background = "#27ae60";
  btn.innerText = "ДОБАВЛЕНО ✓";
  setTimeout(() => { 
    btn.style.background = "#2ecc71"; 
    btn.innerText = "ДОБАВИТЬ В СПИСОК";
  }, 800);
}
</script>
