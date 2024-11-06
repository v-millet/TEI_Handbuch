
## Teil II: Transkription der Handschriften



### 3. Seite / Spalte / physische Zeile
1. Der Beginn einer neuen **Seite** wird getaggt mit `<pb/>` , auch der Beginn der ersten Seite (evtl. bereits in `<front>`, → Kap. 5). Dieses Element ist immer leer. Es steht – wie alle Elemente – immer möglichst weit 'oben' in der xml-Struktur: Bei Handschriften mit abgesetzten Versen also hinter dem Schluss der letzten `<lg>` der vorangehenden Seite, oder, wenn von einem Verspaar ein Vers auf jeder Seite steht, hinter dem Schluss der letzten `<l>`. Bei Handschriften ohne abgesetzte Verse allerdings steht das Element an der ensprechenden Stelle. Es enthält *immer* das Attribut `@n`; der Wert des Attributs ist die Blatt- und Seitenzahl, z.B.: `<pb n="1v"/>`, oder `<pb n="2r"/>`.
2. Der Beginn einer neuen **Spalte** wird getaggt mit `<cb/>`. Dieses Element ist immer leer. In einspaltigen Handschriften steht es immer hinter dem Element `<pb/>`. Bei mehrspaltigen Handschriften steht es außerdem hinter dem letzten Vers oder Verspaar der vorangehenden Spalte und vor der ersten Zeile der neuen Spalte. Es enthält immer das Attribut `@n`; der Wert des Attributs ist der Buchstabe für die jeweilige Spalte (a, b, c), z.B.: `<cb n="a"/>`, oder `<cb n="b"/>`.
3. Der Beginn einer neuen **physischen Zeile** wird getaggt mit `<lb/>`. Dieses Element ist immer leer. Es enthält immer das Attribut `@n`; der Wert des Attributs ist die Nummer der physischen Zeile in der aktuellen Spalte, z.B. `<l><lb n="23"/><w><w><w>`.
4. Die Position von `<lb>` in Bezug zu `<l>` ist im Grunde irrelevant, das `<lb>` kann auch mitten im `<w>` stehen. Aus praktischen Gründen setzen wir überall dort, wo der Versbeginn mit dem Zeilenbeginn zusammenfällt, `<lb>` als erstes Kindelement von `<l>` (s. das Beispiel oben).
Zu Worttrennung → Kap. 9; zu Zeilenüberhängen → Kap. 22.




4. ### Verspaar und Vers
1) Jedes Verspaar steht innerhalb des Elements `<lg>`. Es führt das Attribut `@ana` mit den Werten `"hc:Couplet"` (=Reimpaar, das häufigste), `"hc:Tercet"` oder `"hc:Quatrain"`.
2) Jeder Vers steht innerhalb eines Elements `<l>`. Dieses Element hat drei Attribute: `@n`, `@xml:id` und `@hei:altN`:
   a) Das Attribut `@n` führt als Wert die Versnummer nach der jeweiligen Standard-Edition. Wir benutzen diese Nummerierung als Identifizierung der Verse. Zusatzverse oder Verse, die komplett anders sind aber einen 'Standardvers' an der Stelle ersetzen (sog. 'Ersatzverse') erhalten eine Zusatznummerierung. Zusatznummern bestehen grundsätzlich aus der Standard-Nummer des vorangehenden Verses und (je nach Text und Fachtradition) einen angehängten Buchstaben (z.B. 123a, 123b im Armen Heinrich oder im Gregorius) oder eine durch Komma getrennte Zusatzzahl (z.B. 123,1 123,2 im Iwein).
   b) Das Attribut `@xml:id` (→ Kap. 18) enthält als Wert dieselbe Nummer wie `@n`, mit einem 'l' (wie 'line') und einem Unterstrich davor. Zum Beispiel:
```xml
<l n="123" xml:id="l_123">
<l n="123a" xml:id="l_123a">
<l n="123,1" xml:id="l_123.1">
```    
    (eine `@xml:id` darf kein Komma führen, daher wird dieses durch einen Punkt ersetzt.)
   c) Das Attribut `@hei:altN`, das eine alternative Nummerierung der Verse ermöglicht, zählt die Verse strikt in der Reihenfolge der Handschrift.

Text

