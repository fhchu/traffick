<!DOCTYPE html>
<html lang="en">
<head>
<title> test</title>
<meta charset="UTF-8">
<style>
.jobs{
    visibility: hidden;
    display: none;
}
#button{
    display:none;
}
</style>
</head>
<body>
    <div>
        <label for="name">Name</label>
        <input type="text" id="name">
    </div>

    <div>
        <label for="gender">Gender</label>
        <select id="gender">
            <option value=""></option>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select>
    </div>

    <div id="maleJobs" class='jobs'>
        <label for="job">Employment</label>
        <select id='mjobselect' class="job">
            <option value=""></option>
            <option value="farm">Farm Worker</option>
        </select>
    </div>

    <div id="femaleJobs" class='jobs'>
        <label for="job">Employment</label>
        <select id='fjobselect' class="job">
            <option value=""></option>
            <option value="model">Model</option>
            <option value='waitress'> Waitress </option>
            <option value='caretaker'> Caretaker </option>
        </select>
    </div>
    <button id="button"> Submit </button>
    <p id="story"></p>
    <script>
    const button = document.getElementById('button');
    const genderSelect = document.getElementById('gender');
    const fjob = document.getElementById('femaleJobs');
    const mjob = document.getElementById('maleJobs');
    var name;
    var story;
    var gender;
    var job;
    genderSelect.addEventListener('change', (event) =>{
        gender = genderSelect.value;
        if(gender == 'male'){
            fjob.style.visibility = 'hidden';
            fjob.style.display = 'none';
            mjob.style.visibility = 'visible';
            mjob.style.display = 'block';
        }
        else if(gender == 'female'){
            fjob.style.visibility = 'visible';
            fjob.style.display = 'block';
            mjob.style.visibility = 'hidden';
            mjob.style.display = 'none';
        }
        else{
            button.style.display = 'none';
            fjob.style.visibility = 'hidden';
            fjob.style.display = 'none';
            mjob.style.visibility = 'hidden';
            mjob.style.display = 'none';
            
        }
    });
    fjob.addEventListener('change', (event)=>{
        job = document.getElementById('fjobselect').value;
        if (job == ''){
            button.style.display = 'none';
        }
        else{
            button.style.display = 'block';
            if(job == 'model'){
                story = "You're a young college student in the United States. Strapped for cash, you see a modeling job on Craigslist.";
            }
            else if(job == 'waitress'){
                story = "You're a young woman in northern Vietnam."
            }
            else if (job == 'caretaker'){
                story = "You're a young woman from the Philippines. You find a job in the United States as a health care worker. Upon arrival in San Diego, your passport is taken away and your employer threatens to tell the police you have stolen something. They say you owe $12,000, and that you must work for $300 a month to pay off the debt. Source: https://www.sandiegouniontribune.com/news/public-safety/story/2019-12-01/horrors-of-labor-trafficking-struggle-to-gain-same-public-recognition-as-sex-trafficking"
            }
        }
    });
    mjob.addEventListener('change', (event)=>{
        job = document.getElementById('mjobselect').value;
        if (job == ''){
            button.style.display = 'none';
        }
        else{
            button.style.display = 'block';
            if(job == 'farm'){
                story = "You're a man in mexico";
            }
            else if(job == 'waitress'){
                story = "You're a young woman in northern Vietnam."
            }
        }
    });
    button.addEventListener("click", 
        function (event) {
            name = document.getElementById("name").value;
            story = "Your name is " + name + ". " + story;
            document.getElementById("story").innerHTML = story;
        }
    );
    
    </script>
</body>