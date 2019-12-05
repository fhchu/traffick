  <form>
        <label for="name">Name</label>
        <input type="text" id="name" required>
        <button id="nameButton"> Submit </button>

        <label for="gender">Gender</label>
        <select id="gender" >
            <option value="Man">Male</option>
            <option value="Woman">Female</option>
        </select>

        <button id="genderButton"> Submit </button>
    </form>
    <p id="story"></p>
    <script>
    const nameButton = document.getElementById('nameButton');
    var name;
    var story;
    nameButton.addEventListener("click", 
        function (event) {
            name = document.getElementById("name").value;
            story = "Your name is " + name + ".";
            updateStory();
        }
    );

    function updateStory(){
        document.getElementById("story").innerHTML = story;
    };

    
    </script>