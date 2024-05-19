<template>
    <div id = "display">
            <h1>User profile</h1>
            <img :src="image" >
            <span>Name: </span>
            <b id="name">{{ name }}</b>
            <hr/>
            <span>Email: </span><b id="email">{{ email }}</b>
            <hr/>
            <span>Interests: </span><b id="interests"> {{ interests }}</b>
            <hr>
            <button @click="editProfileButton">Edit Profile</button>
        </div>
      

        <div id ="edit-view">
            <h1>User profile</h1>
            <img :src="image" >
            <span>Name: </span><input type="text" :placeholder="name" id="input-name">
            <hr/>
            <span>Email: </span><input type="email" :placeholder="email" id="input-email">
            <hr/>
            <span>Interests: </span><input type="text" :placeholder="interests" id="input-interests">
            <hr>
            <button @click="updateProfileButton">Update Profile</button>
        </div>
</template>

<script>
    import image from "./1.webp"
    export default {
        name: "App",
        data() {
            return {
                image: image,
                name: "imran",
                email: "imran@gmail.com",
                interests: "coding"
            }
        },
        methods: {
        editProfileButton(){
            var name = document.getElementById('name').textContent
            var inputName = document.getElementById('input-name')
            inputName.value = name

            var email = document.getElementById('email').textContent
            var inputEmail = document.getElementById('input-email')
            inputEmail.value = email

            var interests = document.getElementById('interests').textContent
            var inputInterests = document.getElementById('input-interests')
            inputInterests.value = interests

            document.getElementById("edit-view").style.display = "block"
            document.getElementById("display").style.display = "none"
            
},

        updateProfileButton(){
            var updatedName = document.getElementById("input-name").value
            var name = document.getElementById("name")
            name.textContent = updatedName

            var updatedEmail = document.getElementById("input-email").value
            var email = document.getElementById("email")
            email.textContent = updatedEmail

            var updatedInterests = document.getElementById("input-interests").value
            var interests = document.getElementById("interests")
            interests.textContent = updatedInterests

            document.getElementById("edit-view").style.display = "none"
            document.getElementById("display").style.display = "block"
        }
    }
    }
</script>

<style>
    div{
    width: 80%;
    margin: auto;
}
img{
    width: 350px;
    height: 300px;
    display: block;
    margin-bottom: 30px;
}
b{
    font-size: 20px;
}
hr{
    width: 90%;
    margin: 25px 0;
}

button{
    font-size: 18px;
    padding: 12px 40px;
    border: 2px solid black;
    border-radius: 5px;
    background-color: rgb(226, 226, 226);
}

input{
    padding: 10px;
    font-size: 14px;
    width: 200px;
    font-weight: bolder;
    color: black;
}

#edit-view{
    display: none;
}

#datepicker{
    margin-top: 50px;
}
</style>