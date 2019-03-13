# Chargement de polices

- https://css-tricks.com/snippets/css/using-font-face/
- http://www.bramstein.com/writing/preload-hints-for-web-fonts.html
- https://bitbucket.org/snippets/anamorphik/K5Mbr/the-new-system-font-stack 




## HTML

Utiliser `rel="prefetch"` pour précharger les polices :

```HTML
<!-- pour chaque fichier de police -->
<link rel="prefetch" href="/assets/fonts/fontName/myfont.woff" as="font">
<link rel="prefetch" href="/assets/fonts/fontName/myfont.woff2" as="font">

<!-- font-face definition -->
<link rel="stylesheet" href="/assets/fonts/fontName/fontName.css">
```


## CSS

Utiliser le plus de formats pour le plus large support possible :

```CSS
/* /assets/fonts/fontName/fontName.css */

@font-face {
	font-family: 'fontName';
	src: 	url('webfont.eot'); /* IE9 Compat Modes */
	src: 	url('webfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */
			url('webfont.woff2') format('woff2'), /* Super Modern Browsers */
			url('webfont.woff') format('woff'), /* Pretty Modern Browsers */
			url('webfont.ttf')  format('truetype'), /* Safari, Android, iOS */
      		url('webfont.svg#svgFontName') format('svg'); /* Legacy iOS */
}
```


Appliquer la police en précisant des alternatives (ici Helvetica) en finissant par le type générique (ici sans-serif) :

```CSS
/* styles du thème */

html {
	-webkit-font-smoothing: antialiased;
	font-size: 100%;
	font-family: 'fontName', Helvetica, sans-serif;
}

body {
	font-size: 1rem;
	line-height: 1.4;
	text-rendering: optimizeSpeed;
}

/* Ou uniqument sur certains éléments */
h1, h2, .button {
	font-family: 'fontName', Helvetica, sans-serif;
}
```


## Notes

```CSS
/* 
	Polices systèmes par défaut (large support)
	https://bitbucket.org/snippets/anamorphik/K5Mbr/the-new-system-font-stack 
*/

font-family: -apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen-Sans", "Ubuntu", "Cantarell", "Helvetica Neue", sans-serif;
```



