let contactUsBtn = document.getElementById("contactUsBtn");
let formDetails = {
    email: "",
    firstName: "",
    lastName: ""
}
let url = "https://getform.io/f/awngnpxb";
let options = {
    method: "POST",
    headers: {
        "content-type": "application/json",
        Accept: "application/json"
    },
    body: JSON.stringify(formDetails)
}
contactUsBtn.onclick = function() {
    let email = document.getElementById("email").value;
    let firstName = document.getElementById("firstName").value;
    let lastName = document.getElementById("lastName").value;
    formDetails.email = email;
    formDetails.firstName = firstName;
    formDetails.lastName = lastName;
    fetch(url, options)
        .then(function(response) {
            return response.json()
        })
        .then(function(data) {
            console.log(data)
        })

}

let card1 = document.getElementById("card1")
let card2 = document.getElementById("card2")
let card3 = document.getElementById("card3")
let imageChange = document.getElementById("imageChange");

card1.onclick = function() {
    card1.style.backgroundColor = "red";
    card2.style.backgroundColor = "white";
    card3.style.backgroundColor = "white";
    imageChange.src = "https://res.cloudinary.com/dqzf8y0bc/image/upload/v1721024783/Screenshot_2024-07-15_115559_i6rytn.png";
}

card2.onclick = function() {
    card1.style.backgroundColor = "white";
    card2.style.backgroundColor = "red";
    card3.style.backgroundColor = "white";
    imageChange.src = "https://res.cloudinary.com/dqzf8y0bc/image/upload/v1721024165/Screenshot_2024-07-15_114540_y6f6bh.png";
}
card3.onclick = function() {
    card1.style.backgroundColor = "white";
    card2.style.backgroundColor = "white";
    card3.style.backgroundColor = "red";
    imageChange.src = "https://res.cloudinary.com/dqzf8y0bc/image/upload/v1721024792/Screenshot_2024-07-15_115522_e5jxcl.png";
}