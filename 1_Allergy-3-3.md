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



<!-- Контейнер на 50% ширины экрана -->
<div style="perspective: 1000px; width: 50%; height: 250px; display: inline-block; user-select: none; margin: 10px auto;">
  <div onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
       style="position: relative; width: 100%; height: 100%; transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1); transform-style: preserve-3d; cursor: pointer;">
    
    <!-- ЛИЦЕВАЯ СТОРОНА -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #ffffff; display: flex; align-items: center; justify-content: center; border: 2px solid #2ecc71; border-radius: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); font-family: sans-serif; padding: 20px; box-sizing: border-box; text-align: center;">
      <span style="font-size: 1.5rem; color: #333;">Нажми, чтобы увидеть ответ</span>
    </div>

    <!-- ОБРАТНАЯ СТОРОНА -->
    <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #2ecc71; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 15px; font-family: sans-serif; padding: 20px; box-sizing: border-box; text-align: center;">
      <span style="font-size: 1.5rem;">Это правильный ответ! ✅</span>
    </div>

  </div>
</div>

<!-- ОСНОВНОЙ КОНТЕЙНЕР ДЛЯ КАРТОЧКИ И КНОПКИ -->
<div style="display: flex; align-items: center; gap: 20px; margin-bottom: 50px;">
  
  <!-- КАРТОЧКА (50% ширины) -->
  <div style="perspective: 1000px; width: 50%; height: 150px; user-select: none;">
    <div id="card1" onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
         style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;">
      
      <!-- ЛИЦЕВАЯ СТОРОНА -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: white; display: flex; align-items: center; justify-content: center; border: 2px solid #3498db; border-radius: 12px; font-family: sans-serif; box-sizing: border-box; padding: 10px;">
        <b id="q1">Как по-английски "Яблоко"?</b>
      </div>

      <!-- ОБРАТНАЯ СТОРОНА -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 12px; font-family: sans-serif;">
        <b>Apple</b>
      </div>
    </div>
  </div>

  <!-- КНОПКА РЯДОМ -->
  <button onclick="addToEnd('q1')" style="padding: 15px 25px; border-radius: 8px; border: none; background: #2ecc71; color: white; cursor: pointer; font-weight: bold; font-family: sans-serif;">
    Добавить в список
  </button>
</div>

<hr>

<!-- БЛОК В КОНЦЕ СТРАНИЦЫ -->
<div style="font-family: sans-serif; margin-top: 100px;">
  <h3>Выбранные вопросы:</h3>
  <ul id="selected-list" style="line-height: 1.6; color: #555;">
    <!-- Сюда будут падать вопросы -->
  </ul>
</div>

<!-- СКРИПТ ДЛЯ ДОБАВЛЕНИЯ -->
<script>
function addToEnd(questionId) {
  const text = document.getElementById(questionId).innerText;
  const list = document.getElementById('selected-list');
  
  const li = document.createElement('li');
  li.innerText = text;
  list.appendChild(li);
}
</script>





<!-- Контейнер-строка с фиксированной высотой -->
<div style="display: flex; width: 100%; height: 200px; gap: 10px; margin-bottom: 30px; box-sizing: border-box;">
  
  <!-- КАРТОЧКА (80%) -->
  <div style="perspective: 1000px; width: 80%; height: 100%; user-select: none;">
    <div id="card1" onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
         style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;">
      
      <!-- Лицевая сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #fff; display: flex; align-items: center; justify-content: center; border: 2px solid #3498db; border-radius: 12px; font-family: sans-serif; box-sizing: border-box; padding: 20px; text-align: center;">
        <b id="q1" style="font-size: 1.2rem;">Вопрос: Как работает CSS Flexbox?</b>
      </div>

      <!-- Обратная сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 12px; font-family: sans-serif; box-sizing: border-box; padding: 20px; text-align: center;">
        <span>Это способ выравнивания элементов в контейнере!</span>
      </div>
    </div>
  </div>

  <!-- КНОПКА (20%) -->
  <button onclick="addToEnd('q1')" style="width: 20%; height: 100%; border: none; border-radius: 12px; background: #2ecc71; color: white; cursor: pointer; font-weight: bold; font-family: sans-serif; font-size: 1rem; transition: background 0.3s;">
    СОХРАНИТЬ
  </button>
</div>

<!-- СПИСОК В КОНЦЕ СТРАНИЦЫ -->
<div id="footer-section" style="margin-top: 100px; padding: 20px; font-family: sans-serif; border-top: 2px dashed #ccc;">
  <h3 style="color: #333;">Выбранные вопросы:</h3>
  <ul id="selected-list" style="list-style-type: square; color: #555; line-height: 1.8;">
    <!-- Сюда добавляются вопросы -->
  </ul>
</div>

<script>
function addToEnd(questionId) {
  const text = document.getElementById(questionId).innerText;
  const list = document.getElementById('selected-list');
  
  // Простая проверка на дубликаты
  const items = list.getElementsByTagName('li');
  for (let i = 0; i < items.length; i++) {
    if (items[i].innerText === text) return; 
  }

  const li = document.createElement('li');
  li.innerText = text;
  li.style.padding = "5px 0";
  list.appendChild(li);
  
  // Визуальный отклик кнопки
  event.target.style.background = "#27ae60";
  setTimeout(() => { event.target.style.background = "#2ecc71"; }, 300);
}
</script>












<!-- Контейнер с фиксированной или адаптивной высотой -->
<div style="display: flex; width: 100%; height: 200px; gap: 10px; margin-bottom: 20px; box-sizing: border-box; align-items: stretch;">
  
  <!-- КАРТОЧКА (80%) -->
  <div style="perspective: 1000px; flex: 0 0 80%; user-select: none;">
    <div id="card1" onclick="this.style.transform = (this.style.transform === 'rotateY(180deg)' ? 'rotateY(0deg)' : 'rotateY(180deg)')" 
         style="position: relative; width: 100%; height: 100%; transition: transform 0.6s; transform-style: preserve-3d; cursor: pointer;">
      
      <!-- Лицевая сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #fff; display: flex; align-items: center; justify-content: center; border: 2px solid #3498db; border-radius: 12px; font-family: sans-serif; box-sizing: border-box; padding: 20px; text-align: center;">
        <b id="q1" style="font-size: 1.1rem;">Вопрос: Что такое семантический HTML?</b>
      </div>

      <!-- Обратная сторона -->
      <div style="position: absolute; width: 100%; height: 100%; backface-visibility: hidden; background: #3498db; color: white; transform: rotateY(180deg); display: flex; align-items: center; justify-content: center; border-radius: 12px; font-family: sans-serif; box-sizing: border-box; padding: 20px; text-align: center;">
        <span>Использование тегов по назначению (например, &lt;header&gt;, &lt;footer&gt;).</span>
      </div>
    </div>
  </div>

  <!-- КНОПКА (20%) — Высота наследуется от родителя автоматически -->
  <button onclick="addToEnd('q1', this)" style="flex: 1; border: none; border-radius: 12px; background: #2ecc71; color: white; cursor: pointer; font-weight: bold; font-family: sans-serif; font-size: 1rem; transition: all 0.3s ease; display: flex; align-items: center; justify-content: center; padding: 10px; text-align: center;">
    ДОБАВИТЬ В СПИСОК
  </button>
</div>

<!-- СЕКЦИЯ В КОНЦЕ СТРАНИЦЫ -->
<div style="margin-top: 50px; padding: 20px; font-family: sans-serif; background: #f9f9f9; border-radius: 12px;">
  <h4 style="margin-top: 0;">Ваши закладки:</h4>
  <ul id="selected-list" style="padding-left: 20px;"></ul>
</div>

<script>
function addToEnd(questionId, btn) {
  const text = document.getElementById(questionId).innerText;
  const list = document.getElementById('selected-list');
  
  // Проверка на дубликаты
  const existing = Array.from(list.children).some(li => li.innerText === text);
  if (existing) {
    btn.style.background = "#e74c3c";
    btn.innerText = "УЖЕ ЕСТЬ";
    setTimeout(() => { btn.style.background = "#2ecc71"; btn.innerText = "ДОБАВИТЬ В СПИСОК"; }, 1000);
    return;
  }

  const li = document.createElement('li');
  li.innerText = text;
  li.style.marginBottom = "8px";
  list.appendChild(li);
  
  // Анимация успеха на кнопке
  btn.style.background = "#27ae60";
  btn.innerText = "ДОБАВЛЕНО!";
  setTimeout(() => { 
    btn.style.background = "#2ecc71"; 
    btn.innerText = "ДОБАВИТЬ В СПИСОК"; 
  }, 1000);
}
</script>
