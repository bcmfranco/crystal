<style>

@import url("https://fonts.googleapis.com/css?family=Montserrat");

:root {
	--blue: #44667a;
  --darkest-blue: #2d3238;
  /* --darkest-blue: #ab4fae; */

	--darker-blue: #3c495c;
	--dark-blue: #283e5d;
	--medium-blue: #44667a;
	--light-blue: #5e7e92;
	--lighter-blue: #91a9b9;
	--lightest-blue: #aec0cc;
	
  --white: #ffffff;
	
  --black: #0e1442;
	
  --orange: #ffb300;
	--yellow: #fdd835;

  --bordo: #683131;
  --red: #b92626;

}


* {
  outline: none;
}

*,
*:before,
*:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
}

html,
body {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  -webkit-transition: 0.5s;
  transition: 0.5s;
  background-color: var(--white);
  cursor: default;
  font-family: "Montserrat", sans-serif;
  font-size: 16px;
  background-color: var(--darkest-blue);
}

a {
  text-decoration: none;
  color: var(--white);
  display: block;
  transition-duration: 0.3s;
}

ul {
  list-style-type: none;
  padding: 0;
}

h2 {
}

h3 {
  color: var(--lightest-blue);
  margin: 10px 0;
  text-transform: lowercase;
  font-size: 1.25em;
}

.resume {
  width: 960px;
  background-color: var(--darkest-blue);
  color: var(--white);
  margin: 20px auto;
  position: relative;
  display: flex;
}
.resume .base,
.resume .func {
  box-sizing: border-box;
  float: left;
}
.resume .base > div,
.resume .func > div {
  padding-bottom: 10px;
}
.resume .base > div:last-of-type,
.resume .func > div:last-of-type {
  padding-bottom: 0;
}
.resume .base {
  width: 30%;
  padding: 30px 15px;
  background-color: var(--darker-blue);
  color: var(--white);
  margin: 10px;
}

.resume .base .profile {
  background-color: var(--red);
  padding: 30px 15px 40px 15px;
  margin: -30px -15px 45px -15px;
  position: relative;
  z-index: 2;
}
.resume .base .profile::after {
  content: "";
  position: absolute;
  background-color: var(--darkest-blue);
  width: 100%;
  height: 30px;
  bottom: -15px;
  left: 0;
  transform: skewY(-5deg);
  z-index: -1;
}
.resume .base .profile .photo img {
  width: 100%;
  border-radius: 50%;
}
.resume .base .profile .photo {
  display: flex;
  justify-content: center;
  align-items: center;
}
.resume .base .profile .fa-rocket {
  font-size: 100px;
  text-align: center;
  margin: auto;
  color: var(--darker-blue);
}
.resume .base .profile .info {
  text-align: center;
  color: var(--white);
}
.resume .base .profile .info .name {
  margin-top: 10px;
  margin-bottom: 0;
  font-size: 1.75em;
  text-transform: lowercase;
  color: var(--lightest-blue);
}
.resume .base .profile .info .job {
  margin-top: 10px;
  margin-bottom: 0;
  font-size: 1.5em;
  text-transform: lowercase;
  color: var(--white);
}
.resume .base .contact div {
  line-height: 24px;
}
.resume .base .contact div a:hover {
  color: var(--red);
}
.resume .base .contact div a:hover span::after {
  width: 100%;
}
.resume .base .contact div:hover i {
  color: var(--red);
}
.resume .base .contact div i {
  color: var(--red);
  width: 20px;
  height: 20px;
  font-size: 20px;
  text-align: center;
  margin-right: 15px;
  transition-duration: 0.3s;
}
.resume .base .contact div span {
  position: relative;
}

.resume .base .contact a,
.resume .base .contact p{
  margin: 0px;
  padding: 5px 0px;
}

.resume .base .contact div span::after {
  content: "";
  position: absolute;
  background-color: var(--red);
  height: 1px;
  width: 0;
  bottom: 0;
  left: 0;
  transition-duration: 0.3s;
}
.resume .base .follow .box {
  text-align: center;
  vertical-align: middle;
}
.resume .base .follow .box a {
  display: inline-block;
  vertical-align: text-bottom;
}
.resume .base .follow .box a:hover i {
  background-color: var(--red);
  border-radius: 5px;
  transform: rotate(45deg) scale(0.8);
}
.resume .base .follow .box a:hover i::before {
  transform: rotate(-45deg) scale(1.5);
}
.resume .base .follow .box i {
  display: inline-block;
  font-size: 30px;
  background-color: var(--red);
  width: 60px;
  height: 60px;
  border-radius: 50%;
  line-height: 60px;
  color: var(--darker-blue);
  margin: 0 10px 10px 10px;
  transition-duration: 0.3s;
}
.resume .base .follow .box i::before {
  transition-duration: 0.3s;
}
.resume .base .follow .box i.fa::before {
  display: block;
}
.resume .func {
  width: 100%;
  padding: 30px;
}
.resume .func:hover > div {
  transition-duration: 0.5s;
}
.resume .func:hover > div:hover h3 i {
  transform: scale(1.25);
}
.resume .func:hover > div:not(:hover) {
  opacity: 0.5;
}
.resume .func h3 {
  transition-duration: 0.3s;
  margin-top: 0;
}
.resume .func h3 i {
  color: var(--darker-blue);
  background-color: var(--red);
  width: 42px;
  height: 42px;
  font-size: 20px;
  line-height: 42px;
  border-radius: 50%;
  text-align: center;
  vertical-align: middle;
  margin-right: 8px;
  transition-duration: 0.3s;
}
.resume .func .work,
.resume .func .edu {
  float: left;
}
.resume .func .work small,
.resume .func .edu small {
  display: block;
  opacity: 0.7;
}
.resume .func .work ul li,
.resume .func .edu ul li {
  position: relative;
  margin-left: 15px;
  padding-left: 25px;
  padding-bottom: 15px;
}
.resume .func .work ul li:hover::before,
.resume .func .edu ul li:hover::before {
  animation: circle 1.2s infinite;
}
.resume .func .work ul li:hover span,
.resume .func .edu ul li:hover span {
  color: var(--red);
}
@keyframes circle {
  from {
    box-shadow: 0 0 0 0px var(--red);
  }
  to {
    box-shadow: 0 0 0 6px rgba(255, 255, 255, 0);
  }
}
.resume .func .work ul li:first-of-type::before,
.resume .func .edu ul li:first-of-type::before {
  width: 10px;
  height: 10px;
  left: 1px;
}
.resume .func .work ul li:last-of-type,
.resume .func .edu ul li:last-of-type {
  padding-bottom: 3px;
}
.resume .func .work ul li:last-of-type::after,
.resume .func .edu ul li:last-of-type::after {
  border-radius: 1.5px;
}
.resume .func .work ul li::before,
.resume .func .work ul li::after,
.resume .func .edu ul li::before,
.resume .func .edu ul li::after {
  content: "";
  display: block;
  position: absolute;
}
.resume .func .work ul li::before,
.resume .func .edu ul li::before {
  width: 7px;
  height: 7px;
  border: 3px solid var(--white);
  background: var(--red);
  border-radius: 50%;
  left: 3px;
  z-index: 1;
}
.resume .func .work ul li::after,
.resume .func .edu ul li::after {
  width: 3px;
  height: 100%;
  background: var(--white);
  left: 5px;
  top: 0;
}
.resume .func .work ul li span,
.resume .func .edu ul li span {
  transition-duration: 0.3s;
}
.resume .func .work {
  width: 48%;
  background: var(--darker-blue);
  padding: 15px;
  margin: 0 4% 15px 0;
}
.resume .func .edu {
  width: 48%;
  background: var(--darker-blue);
  padding: 15px;
}
.resume .func .skills-prog {
  clear: both;
  background: var(--darker-blue);
  padding: 15px;
}
.resume .func .skills-prog ul {
  margin-left: 15px;
}
.resume .func .skills-prog ul li {
  margin-bottom: 8px;
  display: flex;
  align-items: center;
  transition-duration: 0.3s;
}
.resume .func .skills-prog ul li:hover {
  color: var(--red);
}
.resume .func .skills-prog ul li:hover .skills-bar .bar {
  background: var(--red);
  box-shadow: 0 0 0 1px var(--red);
}
.resume .func .skills-prog ul li span {
  display: block;
  width: 120px;
}
.resume .func .skills-prog ul li .skills-bar {
  background: var(--white);
  height: 2px;
  width: calc(100% - 120px);
  position: relative;
  border-radius: 2px;
}
.resume .func .skills-prog ul li .skills-bar .bar {
  position: absolute;
  top: -1px;
  height: 4px;
  background: var(--red);
  box-shadow: 0 0 0 var(--red);
  border-radius: 5px;
}
.resume .func .skills-soft {
  clear: both;
  background: var(--darker-blue);
  padding: 15px;
  margin: 15px 0 0;
}
.resume .func .skills-soft ul {
  width: 95%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  text-align: center;
}
.resume .func .skills-soft ul li {
  position: relative;
}
.resume .func .skills-soft ul li:hover svg .cbar {
  stroke: var(--red);
  stroke-width: 4px;
}
.resume .func .skills-soft ul li:hover span,
.resume .func .skills-soft ul li:hover small {
  transform: scale(1.2);
}
.resume .func .skills-soft ul li svg {
  width: 95%;
  fill: transparent;
  transform: rotate(-90deg);
}
.resume .func .skills-soft ul li svg circle {
  stroke-width: 1px;
  stroke: var(--white);
}
.resume .func .skills-soft ul li svg .cbar {
  stroke-width: 3px;
  stroke: var(--red);
  stroke-linecap: round;
}
.resume .func .skills-soft ul li span,
.resume .func .skills-soft ul li small {
  position: absolute;
  display: block;
  width: 100%;
  top: 52%;
  transition-duration: 0.3s;
}
.resume .func .skills-soft ul li span {
  top: 40%;
}
.resume .func .interests {
  background: var(--darker-blue);
  margin: 15px 0 0;
  padding: 15px;
}
.resume .func .interests-items {
  box-sizing: border-box;
  padding: 0 0 15px;
  width: 100%;
  text-align: center;
  display: flex;
  justify-content: space-between;
}
.resume .func .interests-items div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 100px;
  border-radius: 50%;
}
.resume .func .interests-items div:hover i {
  transform: scale(1.2);
}
.resume .func .interests-items div:hover span {
  color: var(--red);
  transition-duration: 0.3s;
}
.resume .func .interests-items div i {
  font-size: 45px;
  width: 60px;
  height: 60px;
  line-height: 60px;
  color: var(--red);
  transition-duration: 0.3s;
}
.resume .func .interests-items div span {
  display: block;
}

.circle-wrap{
  display: grid;
  grid-template-rows: repeat(2, 1fr);
  grid-template-columns: repeat(4, 1fr);
  justify-items: center;
  align-items: center;
}

.circle {
  display: grid;
  align-content: center;
  margin: 10px 0px;
  border: 5px solid var(--red);
  border-radius: 50%;
  width: 120px;
  height: 120px;
  background: inherit;
  text-align: center;
  font-family: Arial;
  font-size: 18px;
  color: var(--white);
}

.circle:hover {
  transition: 0.8s;
  border: 5px solid var(--red);
  width: 130px;
  font-size: 20px;
}

.circle p{
  margin: 0px;
  padding: 5px 0px;
  line-height: 20px;
}


@media only screen and (max-width: 600px) {

  body{
    max-width: 100vw;
  }

  h3{
    transition: transform 250ms;
  }

  h3:hover {
    transform: translateX(30px);
  }


  .resume {
    display: grid;
    margin: 0px auto;
    max-width: 100vw;
  }

  .resume .base {
    width: 90vw;
    height: 585px;
    margin: 0px auto;
    text-align: center;
  }

  .resume .func {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr 2fr;
    margin: 0px auto;
    padding: 0px;
    justify-items: center;
  }

  .resume .func .work,
  .resume .func .edu{
    width: 90vw;
    margin: 10px auto;
    transition: transform 250ms;
  }

  .skills-prog{
    width: 90vw;
    margin: 10px auto;
  }

  .circle-wrap{
    grid-template-columns: repeat(2, 1fr);
  }

}



</style>

<template>
	
	<h1>hola mundo!</h1>

</template>