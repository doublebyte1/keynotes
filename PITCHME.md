#HSLIDE

# Omeletes sem Ovos
### A poor man's GIS

#HSLIDE

![ola](assets/ola.jpg)

#HSLIDE

![culpa](assets/culpa.png)

#HSLIDE

## No fundo...

+ conceito <!-- .element: class="fragment" -->
+ ideia <!-- .element: class="fragment" -->
+ ... <!-- .element: class="fragment" -->

#HSLIDE

![manifesto](assets/manifesto.png)


#HSLIDE

![omeletes](assets/oso.png)

#HSLIDE

![hmmm](assets/hmmm.gif)

#HSLIDE

## Tudo começa com um problema!

---?image=assets/stuck_dog.jpg&size=auto 90%

---?image=assets/cat_tank.jpg&size=auto 90%

---?image=assets/it_guy.jpg&size=auto 85%

#HSLIDE

## Soluções?
+ explicar o problema <!-- .element: class="fragment" -->
+ mostrar um caminho <!-- .element: class="fragment" -->
+ ... <!-- .element: class="fragment" -->
+ continuar <!-- .element: class="fragment" -->

<span style="font-size:0.6em; color:gray">Porque realmente só estva a perder tempo e a aumentar os níveis de frustração</span>

#HSLIDE

## Go <span style="color:#e49436">portable</span>

---?image=assets/go_portable.png&size=auto 90%

#HSLIDE

## OK...
### mas e as aplicações de <span style="color:#e49436">SIG</span>?

#HSLIDE
+ gvSIG <!-- .element: class="fragment" --> 
+ uDig <!-- .element: class="fragment" --> 
+ openJUMP <!-- .element: class="fragment" -->  

#HSLIDE
![gvsig](assets/gvsig.png)
![udig](assets/udig.png)
![openjump](assets/openjump.png)

## Benchmarks

#### Unfortunately, <span style="color:#e49436">ActionCable</span> leaves much to be desired

<span style="font-size:0.6em; color:gray">Press Down key to see charts and gifs</span>

#VSLIDE

## Memory

![memory](assets/Memory3.png)

#VSLIDE

## CPU

![cpu](assets/cpu_chart.gif)

#VSLIDE

## Broadcast Round Trip Time

![rtt](assets/RTT3.png)

#HSLIDE

### Let's extract <span style="color:#e49436">WebSockets</span> somewhere else!

#HSLIDE

## AnyCable

#### Combines the good parts from <span style="color:#e49436">ActionCable</span> with the power of your favorite language for concurrent applications

<span style="font-size:0.6em; color:gray">How it works? See below</span>

#VSLIDE

## How AnyCable Works

![diagram](assets/Scheme2.png)

#VSLIDE

## [gRPC](http://grpc.io)

### Makes AnyCable to be a <span style="color:#e49436">polyglot</span>

#VSLIDE

## AnyCable

#### [Compatible](https://github.com/anycable/anycable#actioncable-compatibility) with ActionCable (channels, javascript, broadcasting)

#### You can still use ActionCable for <span style="color:#e49436">development</span> and <span style="color:#e49436">testing</span>

#VSLIDE

## AnyCable Servers

- [anycable-go](https://github.com/anycable/anycable-go)

- [erlycable](https://github.com/anycable/erlycable)

#VSLIDE

## AnyCable

### [Demo Application](https://github.com/anycable/anycable_demo)

#HSLIDE

## Benchmarks Again

#### AnyCable shows much more better performance.

<span style="font-size:0.6em; color:gray">Press Down key to see charts and gifs</span>

#VSLIDE

## Memory

![memory](assets/Memory5.png)

#VSLIDE

## CPU

![cpu](assets/cpu_chart2.gif)

#VSLIDE

## Broadcast Round Trip Time

![rtt](assets/RTT5.png)


#HSLIDE

## Let's Make ActionCable Not Suck!

[anycable.evilmartians.io](http://anycable.io/)

Vladimir Dementyev [@palkan_tula](http://twitter.com/palkan_tula)

[Evil Martians](http://evilmartians.com)

Twitter [@any_cable](http://twitter.com/any_cable)

GitHub [@anycable](http://github.com/anycable)
