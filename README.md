# Projektseite Spektrometer
von Tim Wähner und David Rettmann                                                                                              
Stormarnschule Ahrensburg                                                                                                              
Klasse 12e                                                                                                                             
Schuljahr 2018/19                                                                                                                      
                                                                                                                                      
                                                                                                                                       
# Inhalt 

## [1. Das Spektrometer](#1)
<details>
  <summary>Genauer</summary>
  
### [Was ist ein optisches Spektrometer?](#1a)

### [Warum haben wir uns für ein optisches Spektrum als Projekt entschieden?](#1b)

</details> <hr>

## [2. Der Arduino](#4)
<details>
  <summary>Genauer</summary>
  
</details> <hr>

## [2. Der Aufbau](#2)
<details>
  <summary>Genauer</summary>
  
### [Anschalten](#2a)
### [Bewegung](#2b)
### [Licht](#2c)
### [Lichtmessung](#2d)
### [Anzeige](#2e)

</details> <hr>

## [3. Die Funktionsweise](#3)
<details> 
  <summary>Beispielversuch</summary>
  
### [Versuchsvorbereitung](#3a)                                                                                          
### [Versuchsdurchführung](#3b)
### [Versuchsnachbereitung / Resultat](#3c)
 </details> <hr>

# 1. Das Spektrometer<a name="1"></a>

## Was ist ein optisches Spektrometer?<a name="1a"></a>

Ein optisches Spektrometer dient der Wellenlängenbestimmung einer einfallenden Strahlung. Dazu wird die Strahlung an einem Gitter gebeugt und bildet somit ein Interferenzmuster. Das Spektrometer dient nun der Winkelbestimmung der Maxima des Interferenzmusters. Aus den Winkeln der Maxima lässt sich so die Wellenlänge der Strahlung bestimmen. 

## Warum haben wir uns für ein optisches Spektrometer als Projekt entschieden?<a name="1b"></a>


# 2. Der Aufbau<a name="2"></a>

## Anschalten<a name="2a"></a>


## Bewegung<a name="2b"></a>

  
## Licht <a name="2c"></a>


## Lichtmessung<a name="2d"></a>

  
## Anzeige<a name="2e"></a>


# 3. Die Funktionsweise<a name="3"></a>

## Funktionsweise und Code 






## Beispielversuch 

Im Folgenden wird ein Versuch und seine Auswertung beschrieben wie er mit unserem Spektrometer durchgeführt werden kann. 

### Versuchsdurchführung<a name="3a"></a>

Vor der eigentlichen Durchführung des Versuches müssen einige Vorbereitungen getroffen werden. Zum einen muss der Arduino an den Computer über das USB Typ-B-Kabel angeschlossen werden, um im Arduino Creator das Monitoring aufzurufen. Außerdem gilt es die Stromversorgung des Motors über eine Steckdose herzustellen. Zusätzlich dazu muss sichergestellt werden, dass der Dreharm sich wirklich auf der Ausgangsposition bei 0° befindet. Zuletzt gilt es die Box wieder "lichtdicht" zu verschließen. Sind all diese Faktoren gegeben kann der Versuch begonnen werden.
Dafür wird lediglich der Schalter auf der Vorderseite umgelegt. Leuchtet nun die blaue Leuchte, läuft der Versuch. Er gilt als beendet und erfolgreich, wenn die rote und grüne LED leuchten. Im Monitor werden nun die Counter 59 & 60 angegeben als Ausschläge. 

// Bild/Video Versuch Schalter und LED 

### Versuchsnachbereitung / Resultat<a name="2c"></a>

Zur Auswertung der Counter wird zunächst der Durchschnitt der ausgeschlagenen Counter berechnet. Dieser beträgt bei unserem Versuch mit dem Laser 59,5. Dieser Wert wird in eine vorbereitete Excel-Tabelle eingetragen, die automatisch den Winkel des Ausschlags und daraus die Wellenlänge des Lasers berechnet. Zusätzlich dazu wird außerdem die Abweichung vom Literaturwert der Wellenlänge des Lasers berechnet. Bei einem Durchschnitt vom 59,5 beträgt der Winkel 41,13° und somit die Wellenlänge &lamba; &lambda;&x039B; 657,8nm. Damit hat unser Wert eine Abweichung von 1,2% vom Literaturwert 650nm. 

// Bild ExcelTabelle und Monitor


## Funktionsweise

Der Laser is an den 3.3V Anschluss des Arduino angeschlossen. Das emittierte Licht ist monochromatisch und fällt durch das Gitter mit 1000 Strichen pro mm. Das Licht wird durch das Huygensche Prinzip gebrochen und interferiert nach dem Gitter. Es entsteht ein Hauptmaximum und links und rechts davon jeweils ein Maximum erster Ordnung (Gangunterschied = nlamda).Mit dem Spektrometer messen wir nun diesen Winkel und bestimmen damit die Wellenlänge des Lichtes des Lasers. Zum messen dient ein Photorsensor, der die Lichteinstrahlung als analoges Signal an den Arduino weitergibt. Der Lichtsensor befindet sich auf einem Dreharm, der von einem Steppermotor konstant gedreht wird. Der Sensor bewegt sich also in konstanter Winkelgeschwindigkeit um 90° von dem Hauptmaximum aus und durchläuft damit ein Nebenmaximum. Damit das Ergebnis genauer ist, befindet sich eine Rhe mit zwei Schlitzen vor dem Sensor, damit nur ein kleiner Bereich des Lichtes einfällt. Im Arduino fällt nun die Information der Zeit mit der Lichtintensität zusammen. Je nachdem in welcher Zeit die Lichtintensität ein gewisses Maß überschreitet, merkt sich der Arduino durch eine Variable diese Stelle. Diese können durch den Monitor angezeigt und so ausgelesen werden. Eingeteilt ist das Intervall in 2x 128 schritte. Da es sich dabei um 90° pro Weg handelt können die Schritte x90/128 gerechnet werden um den Winkel zu erhalten. Mit der Bragg Gleichung lässt sich aus sin() von dem Winkel x die Gitterkonstante 1/1000000 die Wellenlänge des Lichtes errechnen. In unserem finalen Aufbau beleuchten wir den Versuch von der anderen Seite und überprüfen die Funktionsweise unseres Versuches, indem wir mit dem Literaturwert der Wellenlänge (350nm) die Counter bestimmen die die korrekte Wellenlänge ergeben würden. Somit leuchtet die eine Led wenn der Bereich getroffen wurde und die andere wenn außerhalb des Bereiches kein erhöter Lichtausschlag gemessen wurde. Leuchten also beide Lampen war der Versuch erfolgreich.
