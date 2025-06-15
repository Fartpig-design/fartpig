const pigImages = ["pig1.png", "pig2.png", "pig3.png"];
const pigImg = document.getElementById("pigImg");
const fartSound = document.getElementById("fartSound");

document.body.addEventListener("click", (e) => {
  fartSound.currentTime = 0;
  fartSound.play();

  const puff = document.createElement("div");
  puff.className = "puff";
  puff.style.left = `${e.pageX}px`;
  puff.style.top = `${e.pageY}px`;
  puff.innerText = "💨";
  document.body.appendChild(puff);
  setTimeout(() => puff.remove(), 1000);

  let nextImage = pigImages[Math.floor(Math.random() * pigImages.length)];
  pigImg.src = nextImage;
});
