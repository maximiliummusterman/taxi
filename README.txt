Das Taxi-Problem ist eines der bekanntesten Probleme im Bereich des Reinforcement-Learnings. Für die Lösung wird das einfache aber geniale Konzept des Q-Learning verwendet. Dieses funktioniert folgendermaßen: Der Agent bekommt vom System je nach Aktion in einem Zustand eine bestimmte Belohnung. War diese positiv, wird für die Aktion in diesem Zustand der Q-Wert -die Maßzahl für den Agenten, wie gut eine Aktion in einem Zustand ist- in der Tabelle erhöht. Bei einer negativen Belohnung passiert das Umgekehrte. Die Aktualisierung der Q-Werte berücksichtigt auch jeweils den höchsten Q-Wert des Zustandes, der durch die Aktion betreten wird -Eine 'Aktion' ist nichts Weiteres als ein Zustandsübergang, welcher auch auf sich selbst sein kann.-, da dieser Wert angibt, wie gut die beste Aktion im nächsten Zustand ist, bedeutet, wie erstrebenswert dieser nächste Zustand ist. Beim Lernen werden meistens zufällige Aktionen getätigt, um repräsentative Q-Werte zu erhalten. Dies nennt man 'Exploration'. Irgendwann sind die Werte so gut, dass der Agent seine Entscheidung auf dessen Basis trifft, also die Aktion mit dem höchsten Q-Wert ausführt. Dies nennt man 'Exploitation'.
Im Taxi-Problem ist die Umgebung ein 5x5 Feld, in dem der Agent, in diesem Fall das Taxi, bewegt. Dabei gibt es vier besondere Punkte, nur auf diesen kann der Fahrgast aufgenommen und abgesetzt werden. Das Taxi hat die Aufgabe, den Passagier von einem dieser vier Punkte zu einem bestimmten anderen Punkt, ebenfalls aus den vier, zu bringen. Dabei hat das Taxi sechs Möglichkeiten für eine Aktion. Vier davon sind Bewegungsaktionen in die vier Richtungen. Die anderen zwei sind das Aufnehmen und das Absetzen. Man beachte, dass diese Aktionen immer ausgeführt werden, jedoch nicht zwangsläufig zu einer Zustandsänderung führen. Beispiele dafür ist die Aktion 'nach links fahren' bei einer Taxi-Position am linken Rand oder das Absetzen eines Passagiers, obwohl dieser gar nicht im Taxi sitzt. Auf seinem Weg muss der Agent auch den Wänden ausweichen, denn wenn er gegen diese fährt, geschieht ein Unfall und der Versuch scheitert. Nach einem Durchlauf, egal ob erfolgreich oder erfolglos, wird ein neuer Passagier mit einem zufälligen Zielpunkt auf einem zufälligen Startpunkt derselben vier gesetzt. 

Dieses Projekt ist eine Lösung des Taxi-Problems. Die Belohnungen für jede Aktion habe ich wie folgt festgelegt: grundsätzlich -1 (je länger das Taxi braucht, desto schlechter), für willkürliches Absetzen -10, für Fahren gegen eine Wand -50, für das erfolgreiche Absetzen des Passagiers am Zielort +50. Die Struktur des Projektes ergibt sich aus der GUI, dem System, das die Aktionen überwacht und die Belohnungen vergibt, und dem Agenten, der seine Q-Tabelle abspeichert.

+Bediehnungsanleitung+

-Wenn man auf den Start-Button drückt, erscheinen vier dunkelblaue Felder, dies sind die vier besonderen Punkte.
-Die roten Linien repräsentieren die Wände.
-Ein hellblaues Feld bedeutet, dass der Passagier auf diesem Feld ist.
-Ein grünes Feld bedeutet, dass der Passagier zu diesem Feld will.
-Ein dunkelgrünes Feld bedeutet, dass der Passagier auf dem Zielfeld erfolgreich abgesetzt wurde.
-'train(20)' lässt das Taxi 20 Durchläufe machen. 
-'single' lässt das Taxi 1 Durchlauf machen.
-'autotrain' lässt das Taxi so lange Druchläufe machen, bis man auf 'stop autotrain' drückt.
-'new positions' generiert zufällig neue vier dunkelblaue Felder und rote Wände und setzt den Lernprozess, also die Q-Tabelle, zurück.
-'reset q-Table' setzt den Lernprozess zurück.
-'toggle GUI (on/off)' schaltet die GUI an und aus. Eine ausgeschaltete GUI beschleunigt den Lernprozess gewaltig.
-Der Schieberegler nimmt Einfluss auf die Geschwindigkeit des Programms.
-'total training' zeigt die insgesamte Anzahl an Durchläufen in einem Lernprozess an.
-'current moves' zeigt die insgesamte Anzahl an Aktionen in einem Durchlauf an.
-'Ao100 moves Index' zeigt die durchschnittliche Anzahl an Aktionen in den letzten 100 Durchläufen an.
-'sucess rate' zeigt den Anteil der erfoglreichen Durchläufe von den letzten 100 Durchläufen an.
-'passenger alive' bedeutet die Hoffnung auf einen erfolgreichen Durchlauf. 'car crashed...' bedeutet, dass das Taxi gegen eine Wand gefahren ist.
