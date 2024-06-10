<script>
  //script to navigation for header
  document.getElementById('addResearchBtn').addEventListener('click', function(event){
    $('a[data-bs-target="#tab_2"]').tab('show');
  }); 
  
  document.getElementById('manuscript').addEventListener('click', function(event){
    $('a[data-bs-target="#tab_2"]').tab('show');
  }); 

  // Start
  $(document).ready(function () {
    // Function to activate the manuscript tab
    function activateManuscriptTab(tab_name) {
      if(tab_name == "tab_name_2"){
        $('a[data-bs-target="#tab_2"]').tab('show');
      }
      else if(tab_name == "tab_name_5"){
        $('a[data-bs-target="#tab_5"]').tab('show');
      }
    }

    // Check if the URL matches
    if (window.location.href === "http://127.0.0.1:8000/en/profile/?manuscript") {
        activateManuscriptTab("tab_name_2");
    }
    else if (window.location.href === "http://127.0.0.1:8000/en/profile/?saved_list"){
        activateManuscriptTab("tab_name_5");
    }

    // Also bind the click event for the manuscript element
    $("#manuscript").click(function () {
        activateManuscriptTab();
    });
});
// End



 function showTabs(tabId) {
      // Hide all tabs
      $('#tab_1, #tab_2, #tab_3, #tab_4, #tab_5, #tab_44').hide();
      // Remove active class from all tab links
      // $('#protab, #retab, [data-bs-target="#tab_3"], [data-bs-target="#tab_4"], .user_saved_list').removeClass('active');
      $('#protab, #retab, [data-bs-target="#tab_3"], [data-bs-target="#tab_4"], .user_saved_list').removeClass('active');
      // Show the specified tab
      $(tabId).show();
  }
  document.addEventListener('DOMContentLoaded', function() {
    // When Home tab is clicked, open Profile tab
    document.getElementById('home-tab').addEventListener('click', function(event) {      
        event.preventDefault();
        showTabs('#tab_1');
        $('#protab').addClass('active');       
    });

    // When Manuscript tab is clicked, open Research tab
    document.getElementById('manuscript-tab').addEventListener('click', function(event) {      
      event.preventDefault();     
        showTabs('#tab_2');
        $('#retab').addClass('show active');
        $('a[data-bs-target="#tab_2"]').tab('show');
       
    });
});

</script>





<script>
    document.getElementById("manuscript").addEventListener("click", function (event) { 
        window.location.href = '/profile/?manuscript'
        $('#manuscript').click();
       }) 

    document.getElementById("saved_list").addEventListener("click", function (event) {
        window.location.href = '/profile/?saved_list'
        $('#saved_list').click();
    })
</script>
