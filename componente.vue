<template>
  <div class="addNewTable">
    <ul id="novoItemAbaixo" class="nav nav-tabs">
      <li class="nav-item">
        <div @click="addNovaAba" class="nav-link" aria-current="page">
          <i class="mt-1 fas fa-plus-circle fa-lg"></i>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    function addNovaAba () {
      let links = document.querySelectorAll("a");
      links.forEach(link => {
        let div = document.getElementById("novoItemAbaixo");
        //e.preventDefault();
        link.onclick = function () {
          console.log("clicou", link.href);
          var html = "";
          html += `
              <li  class="nav-item">
                  <a class="nav-link active" aria-current="page" href="${link.href}">${link.href}</a>
              </li>`;
          div.innerHTML += html;
       
        };
      });
    
    };
    return {
      addNovaAba,
    };
  },
};
</script>
