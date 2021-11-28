


## Ajouter une "anchor" dans un titre pour faciliter la navigation dans le document

https://stackoverflow.com/questions/5319754/cross-reference-named-anchor-in-markdown


```
### <a name="tith"></a>This is the Heading
Take me to [pookie](#tith)
```

### <a name="tith"></a>This is the Heading
Take me to [pookie](#tith)



## redimentionner les images en markdown

https://stackoverflow.com/questions/14675913/changing-image-size-in-markdown

You could just use some HTML in your Markdown:  

     <img src="drawing.jpg" alt="drawing" width="200"/>

Or via style attribute (not supported by GitHub)  

     <img src="drawing.jpg" alt="drawing" style="width:200px;"/>

Or you could use a custom CSS file as described in this answer on Markdown and image alignment  

     ![drawing](drawing.jpg)
     
CSS in another file:  

     img[alt=drawing] { width: 200px; }
