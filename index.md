---
layout: default
title: "Welcome to Flutterverse"
---
<script src="https://www.google.com/recaptcha/api.js?render=6LdkHZgqAAAAACnGup-JScmY47d3MpbKQOqIvmJZ"></script>

<div class="form-container">
  <h1>Junte-se ao Flutterverse! 🚀</h1>
  <p>Faça parte dessa jornada desde o começo. Inscreva-se hoje e receba atualizações exclusivas enquanto nos preparamos para o lançamento!</p>
  
  <form id="myForm" action="https://script.google.com/macros/s/AKfycbwdj1r-3kSkWcs0YT0Seq6-e3zTPD8AnY_TmqfmHFDcHSj-nSmQ4j520h8HGf5_-BHn/exec" method="POST">
    <input type="text" name="entry.1579886999" placeholder="Nome" required> <!-- Nome -->
    <input type="email" name="entry.407097177" placeholder="Email" required> <!-- Email -->
    <label>
      <input type="checkbox" name="entry.1022838897" value="Quero receber atualizações do Flutterverse"> Quero receber atualizações do Flutterverse
    </label>
    <input type="submit" value="Enviar">
  </form>
</div>

<script>
document.getElementById("myForm").addEventListener("submit", function(event) {
  event.preventDefault();

  const form = this;

  grecaptcha.ready(function() {
    grecaptcha.execute('6LdkHZgqAAAAACnGup-JScmY47d3MpbKQOqIvmJZ', { action: 'submit' }).then(function(token) {
      const recaptchaInput = document.createElement('input');
      recaptchaInput.type = 'hidden';
      recaptchaInput.name = 'g-recaptcha-response';
      recaptchaInput.value = token;
      form.appendChild(recaptchaInput);

      const formData = new FormData(form);

      fetch(form.action, {
        method: "POST",
        body: formData,
        mode: "no-cors"
      }).then(() => {
        window.location.href = "/finish";
      }).catch((error) => {
        console.error("Error submitting the form:", error);
      });
    });
  });
});
</script>