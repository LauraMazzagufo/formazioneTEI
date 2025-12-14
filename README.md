# formazioneTEI
Qui troverete i materiali che sono stati usati durante la giornata di formazione sulla codifica in XML-TEI:


## 1. documento "test.xml"
Vai al [documento](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/test.xml)

Riferimento slide: #10 - Introduzione > XML (eXtensible Markup Language)

Semplice documento XML.


## 2. documento "LL1_7.xml"
Vai al [documento](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/LL1_7.xml)

Riferimento slide: #24 - TEI > Metadati in teiHeader (e segg.)

Si tratta della codifica di una lettera di Vincenzo Bellini, raccolta nell'edizione [Bellini Digital Correspondence](https://bellinicorrespondence.cnr.it/ledizione-digitale/). Si può visitare l'edizione [e in particolare la pagina web che illustra questa lettera](https://bellinicorrespondence.cnr.it/evt/build/#/imgTxt?d=LL1.7&p=LL1.7_fol_1r&s=div_102&e=diplomatic&ce=interpretative), leggere i [criteri editoriali e di codifica](https://bellinicorrespondence.cnr.it/scelte-editoriali/), oppure scaricare [il repository con tutti file XML sorgenti](https://dspace-clarin-it.ilc.cnr.it/items/2e6fe73a-db5c-48aa-ad0a-dcaecc0baddb) dai quali è stata realizzata l'edizione. 



## 3-4. immagini "LL1.7_0001.jpg" e "LL1.7_0002.jpg"
Vai all'[immagine 01](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/LL1.7_0001.jpg) e all'[immagine 02](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/LL1.7_0002.jpg)

Riferimento slide: #32 - TEI > Dalla teoria alla pratica (e segg.)



## 5. documento "lettera_modello.xml"
Vai al [documento](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/lettera_modello.xml)

Riferimento slide: #33 - TEI > correspDesc (e segg.)

Modello di codifica per una lettera, tratto da LL1_7.xml, con spiegazioni e commenti.


## 6. documento "lettera_da-compilare.xml"
Vai al [documento](https://github.com/LauraMazzagufo/formazioneTEI/blob/main/lettera_da-compilare.xml)

Riferimento slide: #49 - Dalla teoria alla pratica > Codifica di un testo epistolare

Si tratta del documento "lettera_modello.xml", ma modificato in modo tale da compilarlo in aula, come esercizio di codifica (tagset `correspDesc` e parte del `body`).

Qui modifiche effettuate:
```xml
<!-- correspDesc: -->
<!-- ############################################ ESERCIZIO DI CODIFICA #######################################-->
<correspDesc>
	<correspAction type="sent">
		<persName ref="#AmilcarePonchielli">Amilcare Ponchielli</persName>
		<placeName ref="#Milano">Milano</placeName>
		<date when="1882-12-05">5 dicembre 1882</date>
	</correspAction>

	<correspAction type="received">
		<persName ref="#TeresinaBrambilla">Teresina Brambilla</persName>
		<placeName ref="#Livorno">Livorno</placeName>
		<date>unknown</date>
	</correspAction>

	<correspContext>
		<p>Non si conosce il contesto di riferimento.</p>
	</correspContext>
	
</correspDesc>
<!-- ############################################ ESERCIZIO DI CODIFICA #######################################-->
			
<!-- liste in surceDesc -->
<listPerson>
	<person xml:id="AmilcarePonchielli">
		<ref type="VIAF" target="http://viaf.org/viaf/10034325"/>
		<ref type="DNB" target="http://d-nb.info/gnd/119060507"/>
		<forename>Amilcare</forename>
		<surname>Ponchielli</surname>
		<sex>M</sex>
		<birth>
			<date when="1834">1834</date>
			<placeName>Paderno Fasolaro</placeName>
		</birth>
		<death>
			<date when="1886">1886</date>
			<placeName>Milano</placeName>
		</death>
		<note>
			<p>Compositore italiano.</p>
		</note>
	</person>

	<person xml:id="TeresinaBrambilla">
		<ref type="VIAF" target="http://viaf.org/viaf/64341188"/>
		<forename>Teresina</forename>
		<surname>Brambilla</surname>
		<sex>F</sex>
		<birth>
			<date when="1845">1845</date>
			<placeName>Cassano d'Adda</placeName>
		</birth>
		<death>
			<date when="1921">1921</date>
			<placeName>Vercelli</placeName>
		</death>
		<note>
			<p>Soprano italiano, moglie di Amilcare Ponchielli.</p>
		</note>
	</person>
</listPerson>

<listPlace>
	<place xml:id="Milano">
		<placeName ref="https://www.geonames.org/3173435/">Milano</placeName>
		<country key="IT">Italia</country>
		<note></note>
	</place>

	<place xml:id="Livorno">
		<placeName ref="https://www.geonames.org/3174659/">Livorno</placeName>
		<country key="IT">Italia</country>
		<note></note>
	</place>
</listPlace>


<!-- trascrizione testo nel body -->
<body xml:lang="it"> <!-- lettera vera e propria -->
	<pb n="2" />


	<div type="content">
		<opener>
			<salute>
				<hi rend="underline">Cara el me nuli</hi>
			</salute>
			<dateline>
				<date when="1882-10-5">5 10.bre 1882.</date>
			</dateline>
			<placeName ref="#Milano">Milano</placeName>
		</opener>
		<lb />Ho ricevuto oggi la
		<lb />tua in data del 3 coi giornali e gli articoli staccati che consegnerò al
		<lb /><hi rend="underline">Trovatore</hi>. <persName ref="#Bedogni">Bedogni</persName>è assente da Milano – si trova a Genova, dove io 
		<lb />gli ho spedito una lettera per Rossi raccomandandolo perché possa 
		<lb />presentarlo alla<hi rend="underline"><persName ref="#Badino">Badino</persName></hi>. 
		<lb />[...] gli amici - 
		<closer>
			T'invio i soliti abbracci per parte della <rs>zia</rs>, zie etc. - 
			<lb />Gildo<supplied resp="#NT">,</supplied> Mariettina, e baminoni e da me abbiti sempre infiniti baci dal 
			<salute>
				tuo 
				<choice>
					<abbr>aff.<sup>o</sup></abbr>
					<expan>aff<supplied resp="#NT">[ettuos]</supplied>o</expan>
				</choice>
				nuli
			</salute>
			<signed>
				<persName ref="#AmilcarePonchielli">Amilcare</persName>
			</signed>
		</closer>
		<postscript>
			<p>Tante cose per parte della <rs>Maestra</rs></p>
		</postscript>
	</div>
</body>
```
