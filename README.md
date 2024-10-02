# iPhone 15 Website Clone

<div align="center">
  <br />
    <img src="https://i.postimg.cc/37PnQw8n/Image-from.png" alt="Project Banner">
  <br />

  <div>
    <img src="https://img.shields.io/badge/-React_JS-black?style=for-the-badge&logoColor=white&logo=react&color=61DAFB" alt="react.js" />
    <img src="https://img.shields.io/badge/-Three_JS-black?style=for-the-badge&logoColor=white&logo=threedotjs&color=000000" alt="three.js" />
    <img src="https://img.shields.io/badge/-GSAP-black?style=for-the-badge&logoColor=white&logo=greensock&color=88CE02" alt="greensock" />
    <img src="https://img.shields.io/badge/-Tailwind_CSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=06B6D4" alt="tailwindcss" />
  </div>

  <h3 align="center">iPhone 15 Website</h3>

  <div align="center">
    Build this project step by step with my detailed tutorials. Join me on this journey!
  </div>
</div>

## 📋 Table of Contents

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 🔋 [Features](#features)
4. 🤸 [Quick Start](#quick-start)
5. 🕸️ [Snippets](#snippets)
6. 🔗 [Links](#links)
7. 🚀 [More](#more)

## 🚨 Tutorial

This repository contains the code for an in-depth tutorial. If you prefer visual learning, this is a great resource to help you build projects step-by-step in a beginner-friendly manner!

## <a name="introduction">🤖 Introduction</a>

This project is a clone of Apple's iPhone 15 Pro website built using React.js and TailwindCSS. It showcases the use of GSAP (Greensock Animations) and Three.js to display iPhone 15 Pro models in various colors and shapes.

You can view the live application [here](https://i-phone-main.vercel.app/).

## <a name="tech-stack">⚙️ Tech Stack</a>

- React.js
- Three.js
- React Three Fiber
- React Three Drei
- GSAP (Greensock)
- Vite
- Tailwind CSS

## <a name="features">🔋 Features</a>

👉 **Smooth Animations with GSAP**: Enhance user experience with captivating animations powered by GSAP.

👉 **3D Model Rendering**: Explore the iPhone 15 Pro from different angles with dynamic 3D rendering.

👉 **Custom Video Carousel**: Engage users with an interactive video carousel developed using GSAP.

👉 **Responsive Design**: Consistent access on any device with a fully responsive design.

## <a name="quick-start">🤸 Quick Start</a>

Follow these steps to set up the project locally.

**Prerequisites**

Make sure you have the following installed:

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/en)
- [npm](https://www.npmjs.com/)

**Cloning the Repository**

```bash
git clone https://github.com/Qusai007/IPhone-main.git
cd IPhone-main
```

**Installation**

Install the project dependencies:

```bash
npm install
```

**Running the Project**

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser to view the project.

## <a name="snippets">🕸️ Snippets</a>

<details>
<summary><code>tailwind.config.js</code></summary>

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {
      colors: {
        blue: "#2997FF",
        gray: {
          DEFAULT: "#86868b",
          100: "#94928d",
          200: "#afafaf",
          300: "#42424570",
        },
        zinc: "#101010",
      },
    },
  },
  plugins: [],
};
```

</details>

<details>
<summary><code>constants/index.js</code></summary>

```javascript
import {
  blackImg,
  blueImg,
  highlightFirstVideo,
  highlightFourthVideo,
  highlightSecondVideo,
  highlightThirdVideo,
  whiteImg,
  yellowImg,
} from "../utils";

export const navLists = ["Store", "Mac", "iPhone", "Support"];

export const hightlightsSlides = [
  {
    id: 1,
    textLists: [
      "Enter A17 Pro.",
      "Game‑changing chip.",
      "Groundbreaking performance.",
    ],
    video: highlightFirstVideo,
    videoDuration: 4,
  },
  {
    id: 2,
    textLists: ["Titanium.", "So strong. So light. So Pro."],
    video: highlightSecondVideo,
    videoDuration: 5,
  },
  {
    id: 3,
    textLists: [
      "iPhone 15 Pro Max has the",
      "longest optical zoom in",
      "iPhone ever. Far out.",
    ],
    video: highlightThirdVideo,
    videoDuration: 2,
  },
  {
    id: 4,
    textLists: ["All-new Action button.", "What will yours do?."],
    video: highlightFourthVideo,
    videoDuration: 3.63,
  },
];

export const models = [
  {
    id: 1,
    title: "iPhone 15 Pro in Natural Titanium",
    color: ["#8F8A81", "#ffe7b9", "#6f6c64"],
    img: yellowImg,
  },
  {
    id: 2,
    title: "iPhone 15 Pro in Blue Titanium",
    color: ["#53596E", "#6395ff", "#21242e"],
    img: blueImg,
  },
  {
    id: 3,
    title: "iPhone 15 Pro in White Titanium",
    color: ["#C9C8C2", "#ffffff", "#C9C8C2"],
    img: whiteImg,
  },
  {
    id: 4,
    title: "iPhone 15 Pro in Black Titanium",
    color: ["#454749", "#3b3b3b", "#181819"],
    img: blackImg,
  },
];

export const sizes = [
  { label: '6.1"', value: "small" },
  { label: '6.7"', value: "large" },
];

export const footerLinks = [
  "Privacy Policy",
  "Terms of Use",
  "Sales Policy",
  "Legal",
  "Site Map",
];
```

</details>

<details>
<summary><code>Lights.jsx</code></summary>

```javascript
import { Environment, Lightformer } from "@react-three/drei";

const Lights = () => {
  return (
    <group name="lights">
      <Environment resolution={256}>
        <group>
          <Lightformer
            form="rect"
            intensity={10}
            position={[-1, 0, -10]}
            scale={10}
            color={"#495057"}
          />
          <Lightformer
            form="rect"
            intensity={10}
            position={[-10, 2, 1]}
            scale={10}
            rotation-y={Math.PI / 2}
          />
          <Lightformer
            form="rect"
            intensity={10}
            position={[10, 0, 1]}
            scale={10}
            rotation-y={Math.PI / 2}
          />
        </group>
      </Environment>

      <spotLight
        position={[-2, 10, 5]}
        angle={0.15}
        penumbra={1}
        decay={0}
        intensity={Math.PI * 0.2}
        color={"#f8f9fa"}
      />
      <spotLight
        position={[0, -25, 10]}
        angle={0.15}
        penumbra={1}
        decay={0}
        intensity={Math.PI * 0.2}
        color={"#f8f9fa"}
      />
      <spotLight
        position={[0, 15, 5]}
        angle={0.15}
        penumbra={1}
        decay={0.1}
        intensity={Math.PI * 3}
      />
    </group>
  );
};

export default Lights;
```

</details>

<details>
<summary><code>VideoCarousel.jsx</code></summary>

```javascript
import gsap from "gsap";
import { useGSAP } from "@gsap/react";
import { ScrollTrigger } from "gsap/all";
gsap.registerPlugin(ScrollTrigger);
import { useEffect, useRef, useState } from "react";

import { hightlightsSlides } from "../constants";
import { pauseImg, playImg, replayImg } from "../utils";

const VideoCarousel = () => {
  const videoRef = useRef([]);
  const videoSpanRef = useRef([]);
 

 const [currentIndex, setCurrentIndex] = useState(0);

  useEffect(() => {
    const tl = gsap.timeline({
      scrollTrigger: {
        trigger: "#videoCarousel",
        start: "top top",
        end: "bottom bottom",
        scrub: true,
      },
    });

    tl.to(videoRef.current[currentIndex], { opacity: 1, duration: 0.5 })
      .to(videoRef.current[currentIndex], { opacity: 0, duration: 0.5 }, "+=3")
      .to(videoRef.current[currentIndex], { opacity: 0, duration: 0.5 });

    return () => {
      tl.kill();
    };
  }, [currentIndex]);

  const handleVideoChange = (index) => {
    if (index !== currentIndex) {
      setCurrentIndex(index);
    }
  };

  return (
    <div className="relative" id="videoCarousel">
      {hightlightsSlides.map((slide, index) => (
        <video
          key={slide.id}
          ref={(el) => (videoRef.current[index] = el)}
          className="absolute inset-0 w-full h-full object-cover opacity-0"
          src={slide.video}
          loop
          muted
        />
      ))}
      <div className="flex justify-center space-x-4 absolute inset-0 top-1/2">
        {hightlightsSlides.map((slide, index) => (
          <button
            key={slide.id}
            onClick={() => handleVideoChange(index)}
            className={`${
              currentIndex === index ? "bg-blue-500" : "bg-gray-300"
            } p-2 rounded`}
          >
            {index + 1}
          </button>
        ))}
      </div>
    </div>
  );
};

export default VideoCarousel;
```

</details>

- [My GitHub](https://github.com/Qusai007/)
- [My LinkedIn](https://www.linkedin.com/in/qusai-johar/)
- [My Instagram](https://www.instagram.com/official_qusai_johar/)

## <a name="more">🚀 More</a>

If you found this tutorial helpful, please consider giving it a star! ⭐