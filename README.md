 🏄 # Project-9 Tropical Paradise 🏄
SASS / HTML / CSS / JS
Font Awesome 

Google Fonts
+     Dancing Script
      https://fonts.google.com/specimen/Dancing+Script?query=dancing+script
+      Open Sans
       https://fonts.google.com/specimen/Open+Sans
CSS = SCSS = main.scss   
+		@import './colors';
+		@import './components';
+		@import './mixins';

+		*,
+		*::before,
+		*::after {
+		box-sizing: border-box;
		margin: 0;
		padding: 0;
		}
+		html {
			font-size: 62.5%;
			scroll-behavior: smooth;
		}
+		body {
			font-family: 'Open Sans', sans-serif;
			font-size: 1.6rem;
		}
CSS = NAV = burger
+      .burger-btn {
	      position: fixed;
	      top: 20px;
	      right: 20px;
	      padding: 1em;
	      background: none;
	      border: 1px solid transparent;
	      cursor: pointer;
	      z-index: 1000;

+      	&:focus {
	      	outline: none;
		      border: 1px solid rgba(255, 255, 255, 0.5);
      		border-radius: 8px;
	      }

+          &:hover {
              .burger-btn__bars::after, .burger-btn__bars::before {
                  width: 100%;
              }
          }

+      	&__box {
	      	position: relative;
		      width: 40px;
		      height: 30px;
	      }
+      	&__bars,
	      &__bars::after,
	      &__bars::before {
		      @include burgerBtn;
	      }
+          &__bars {
              width: 100%;
        
+              &::after {
                  top: 13px;
                  width: 60%;
              }
+              &::before {
                  top: 27px;
                  width: 30%;
                  transition-delay: .1s;
              }
          }
CSS = SCSS = nav - big = main.scss
+		.nav {
			position: fixed;
			top: 0;
			display: flex;
			justify-content: center;
			align-items: center;
			height: 100vh;
			width: 100%;
 			transform: translateX(100%);
 			transition: 0.5s cubic-bezier(0.65, 0.05, 0.36, 1);
			background-image: $blue-gradient-solid;
			z-index: 100;
+		&--active {
			transform: translateX(0);
		}
   
+		&__item {
			position: relative;
			display: block;
			margin: 0.5em 0;
			padding: 0.5em 2em;
			font-size: 2.8rem;
			color: $pure-white;
			text-decoration: none;
+		&::before {
			position: absolute;
			top: 0;
			left: 0;
			width: 3px;
			height: 100%;
			transform: scaleY(0);
			background-color: $pure-white;
			transition: transform .3s;
			content: '';
		}
+		&:hover::before {
			transform: scaleY(1);
			}
		}

CSS = HEADER = IMG main.scss
+		.header {
			position: relative;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
			padding: 2em;
			height: 75vh;
			text-align: center;
			color: $pure-white;
			@include heroImages('../img/header-mini.jpg');
			background-attachment: scroll;

+			&__heading {
				font-family: 'Dancing Script', cursive;
				font-size: 4.8rem;
				font-weight: 300;
			}
+			&__text {
				font-size: 1.4rem;
			}
+			&__btn {
				margin-top: 2em;
				padding: 0.8em 1.6em;
				background: $pure-white;
				border: none;
				border-radius: 8px;
				color: $dark;
				text-decoration: none;
				text-transform: uppercase;
				cursor: pointer;

+				&::before {
					background-color: $light-white;
				}
			}
CSS = SCSS = Media = main.scss
+		@media (min-width: 768px) {
			.white-block {
				height: 50px;
				width: 45%;
			}
			.header {
				&__heading {
					font-size: 6.6rem;
			}	
			&__text {
				font-size: 2.2rem;
			}
			&__btn {
				font-size: 1.6rem;
			}
		}
	}
+		@media(min-width: 992px) {
			.burger-btn {
				top: 50px;
				right: 50px;
			}
    		.header {
        		background-image: $blue-gradient,url('../img/header-big.jpg');
    
        		&__heading {
        	    		font-size: 10rem;
        		}
    		}
  	} 

CSS = Header = _components.scss
+		.wrapper {
			margin: 0 auto;
			width: 100%;
			max-width: 1200px;
		}
+		.white-block {
			position: absolute;
			height: 40px;
			width: 60%;
			background-color: $pure-white;

+			&-left {
				bottom: 0;
				left: -50px;
				transform: skew(45deg);
			}
+			&-right {
				top: 0;
				right: -50px;
				transform: skew(45deg);
			}
		}
+		.btn-special-animation {
			position: relative;
			transition: background-color 0.3s;
			overflow: hidden;
			z-index: 0;

+			&::before {
				display: block;
				content: '';
				position: absolute;
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				transform: scaleX(0);
				transform-origin: right;
				transition: transform 0.3s;
				z-index: -1;
			}
+		    &:hover::before {
        		transform: scaleX(1);
        		transform-origin: left;
    		}
             } 
CSS = NAV / Header = _mixins.scss
+		@mixin burgerBtn {
    			position: absolute;
    			right: 0;
    			height: 3px;
    			content: '';
    			background-color: $pure-white;
    			transition: width .3s;
			}
+			@mixin heroImages($bgImg) {
    				background-image: $blue-gradient, url($bgImg);
    				background-size: cover;
    				background-position: center;
    				background-attachment: fixed;
				}
CSS = SCSS = _colors.scss
+		$main-color: #1755e7;
		$secondary-color: #164dcc;
		$pure-white: #fff;
		$light-white: #eee;
		$dark: #2e2e2e;
		$green-color: #00ffaa;
		$green-color-hover: #0fe29c;

+		$light-blue-gradient: linear-gradient(45deg, rgba(8, 206, 255, 0.75), rgba(8, 24, 255, 0.75));
		$blue-gradient: linear-gradient(45deg, rgba(20, 105, 241, 0.75), rgba(42, 10, 184, 0.75));
		$purple-gradient: linear-gradient(45deg, rgba(190, 10, 214, 0.75), rgba(68, 0, 255, 0.75));
		$blue-gradient-solid: linear-gradient(45deg, rgb(20, 105, 241), rgb(42, 10, 184));
		$light-blue-gradient-solid: radial-gradient(circle at top right, rgb(0, 78, 255) 0%, rgb(0, 212, 255) 100%);
