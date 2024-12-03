---
layout: default
title: "Welcome to Flutterverse"
---
<div class="form-container">
<h1>Junte-se ao Flutterverse! 🚀</h1>
<p>Faça parte dessa jornada desde o começo. Inscreva-se hoje e receba atualizações exclusivas enquanto nos preparamos para o lançamento!</p>
<form id="myForm" action="https://script.google.com/macros/s/AKfycbxUxNPgT-frXjtMhcajStBNeW1T56J1NHEInwID4P4r1QaUqx20a14lSaBjx45jiZyS/exec" method="POST">
  <input type="text" name="entry.1579886999" placeholder="Nome" required> <!-- Nome -->
  <input type="email" name="entry.407097177" placeholder="Email" required> <!-- Email -->
  <label>
    <input type="checkbox" name="entry.1022838897" value="Quero receber atualizações do Flutterverse"> Quero receber atualizações do Flutterverse <!-- Radio Button -->
  </label>
  <input type="submit" value="Enviar">
</form>
</div>

<script>
  document.getElementById("myForm").addEventListener("submit", function(event) {
    event.preventDefault(); 

    var formData = new FormData(this);

    fetch(this.action, {
      method: "POST",
      body: formData,
      mode: "no-cors"
    }).then(response => {
        window.location.href = "/finish";
    });
    
    
  });
</script>