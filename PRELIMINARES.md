
# PRELIMINARES


## 1. Instalar Clojure

*Instrucciones para instalar Clojure y un editor de código (LightTable).*

Un par de cosillas:

**Clojure usa Java, por lo que necesitamos tenerlo instalado antes de nada.**

En linux, Java viene instalado, en MacOSX puedes encontrar [el instalador aquí](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

**En vez de instalar Clojure, vamos a instalar otro programa que instala Clojure** (ese programa es leiningen). Esta es la típica solución informática: en vez de resolver un problema, haz un programa que lo resuelva, o dicho de otro modo: cualquier problema informático se resuelve añadiendo una capa de indirección (también conocido como "cualquier problema de rendimiento se resuelve quitando una capa de indirección"). En cualquier caso, instalemos leiningen utilizando la consola (aka 'línea de comando', ver abajo):

```
wget https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein
mv lein /usr/local/bin
chmod +x /usr/local/bin/lein
lein --version
```

Si todo ha ido bien deberíamos ver algo como:
```
Leiningen 2.5.0 on Java 1.6.0_65 Java HotSpot(TM) 64-Bit Server VM
```
Bien, tenemos Leinigen instalado. Vamos a decirle que instale Clojure. O más exactamente: vamos a decirle que cree un proyecto que use Clojure:

```
lein new holacloj
cd holacloj
lein repl
```

Si al final de eso veis ```user=>``` es que leiningren ha hecho su trabajo. Enhorabuena, y benvenidx al mundo Clojure donde todo es funcionalmente raro...

---

### Extra: instala LightTable

LightTable es un editor de texto (entre otras cosas) pensado para Clojure. Descárgalo en [su web](http://lighttable.com/). En Mac es necesario mover el fichero descargado a ```usr/local/bin``` si quieres usarlo desde la consola. Truco: arrastra un fichero del finder a la consola para ver su nombre completo, en mi caso:

```
mv /Users/Dani/Downloads/Light Table/light /usr/local/bin
```

### Extra: añade Overtone

Idea para darle emoción: edita el fichero ```project.clj``` y añade (Overtone)[http://overtone.github.io/] como dependencia:

```
:dependencies [
                 [org.clojure/clojure "1.6.0"]
                 [overtone "0.9.1"]]
```

Genera sonidos con la [REPL](http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop):
```
lein repl
(use 'overtone.live)
(def sin-synth (synth (out 0 (pan2 (sin-osc 440)))))
(sin-synth)
(stop)
```

Más información aquí: https://github.com/overtone/overtone/wiki/Getting-Started

### Extra: la consola

- ¿Es necesario usar la línea de comando?
- Si
- Pero, si no se ni lo que es...
- En Ubuntu y en Mac es una aplicación llamada "Terminal"
- Pero.... tengo windows....
- Tendrás que apañarte. Creo que se llama cgywin
- Y ¿para qué sirve?
- Para ser un hacker
- Pero... es que está muy oscuro..
- Si
