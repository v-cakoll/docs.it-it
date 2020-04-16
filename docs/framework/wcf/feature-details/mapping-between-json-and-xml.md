---
title: Mapping tra JSON e XML
ms.date: 03/30/2017
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
ms.openlocfilehash: 55812ad15d1f38bb0c295e6895dfff329035206d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464060"
---
# <a name="mapping-between-json-and-xml"></a>Mapping tra JSON e XML
I lettori e i writer prodotti da <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> forniscono una API XML sul contenuto JSON (JavaScript Object Notation). JSON codifica i dati utilizzando un sottoinsieme dei valori letterali di oggetto di JavaScript. I lettori e i writer prodotti da questa factory vengono utilizzati anche quando il <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> contenuto <xref:System.ServiceModel.WebHttpBinding>JSON viene inviato o ricevuto da applicazioni Windows Communication Foundation (WCF) utilizzando o .

In caso di inizializzazione con contenuto JSON, il lettore JSON si comporta nello stesso modo di un lettore XML testuale su un'istanza di XML. Il writer JSON, in presenza di una sequenza di chiamate prodotte da una certa istanza XML su un lettore XML testuale, scrive il contenuto JSON. In questo argomento viene illustrato il mapping tra questa istanza di XML e il contenuto JSON, per l'utilizzo in scenari avanzati.

Internamente, JSON è rappresentato come un infoset XML quando viene elaborato da WCF. In genere non è necessario occuparsi di questa rappresentazione interna poiché il mapping è solo logico: JSON non viene normalmente convertito fisicamente in XML in memoria né in JSON da XML. Il mapping significa che le API XML sono utilizzate per accedere a contenuto JSON.

Quando WCF utilizza JSON, lo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> scenario usuale è che <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> l'oggetto <xref:System.ServiceModel.Description.WebHttpBehavior> viene collegato automaticamente dal comportamento o dal comportamento quando appropriato. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è in grado di comprendere il mapping tra JSON e l'infoset XML e si comporta come se stesse interagendo direttamente con JSON. È possibile utilizzare <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> con qualsiasi lettore o writer XML, a condizione che XML sia conforme al mapping seguente.

Negli scenari avanzati, può rendersi necessario accedere direttamente al mapping seguente. Questi scenari si verificano quando si desidera serializzare e deserializzare JSON in modalità personalizzate, senza basarsi su <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>o quando si interagisce direttamente con il tipo <xref:System.ServiceModel.Channels.Message> per messaggi che contengono JSON. Il mapping JSON-XML è utilizzato anche per la registrazione dei messaggi. Quando si usa la funzionalità di registrazione dei messaggi in WCF, i messaggi JSON vengono registrati come XML in base al mapping descritto nella sezione successiva.

Per chiarire il concetto di mapping, l'esempio seguente fa riferimento a un documento JSON.

```json
{"product":"pencil","price":12}
```

Per leggere il documento JSON tramite uno dei lettori indicato in precedenza, utilizzare la stessa sequenza di chiamate a <xref:System.Xml.XmlDictionaryReader> utilizzata per leggere il documento XML seguente.

```xml
<root type="object">
    <product type="string">pencil</product>
    <price type="number">12</price>
</root>
```

Inoltre, se il messaggio JSON nell'esempio viene ricevuto da WCF e registrato, il frammento XML verrà visualizzato nel log precedente.

## <a name="mapping-between-json-and-the-xml-infoset"></a>Mapping tra JSON e l'InfoSet XML

Formalmente, il mapping è tra JSON come descritto in [RFC 4627](https://www.ietf.org/rfc/rfc4627.txt) (ad eccezione di alcune restrizioni relaxed e alcune altre restrizioni aggiunte) e l'infoset XML (e XML non testuale) come descritto in [XML Information Set](https://www.w3.org/TR/2004/REC-xml-infoset-20040204/). Vedere questo argomento per le definizioni di elementi di *informazioni* e campi in [parentesi quadre].

Un documento JSON vuoto è mappato a un documento XML vuoto e un documento XML vuoto viene mappato a un documento JSON vuoto. Nel mapping da XML a JSON non sono consentiti gli spazi vuoti precedenti e gli spazi vuoti finali dopo il documento.

Il mapping viene definito tra un DII (Document Information Item) o un EII (Element Information Item) e JSON. La proprietà [elemento del documento] di EII o DII, viene chiamata elemento JSON radice. Si noti che in questo mapping non sono supportati frammenti di documento (XML con più elementi radice).

Esempio: il documento seguente.

```xml
<?xml version="1.0"?>
<root type="number">42</root>
```

E l'elemento seguente:

```xml
<root type="number">42</root>
```

Entrambi hanno un mapping a JSON. Il `root` <elemento> è l'elemento JSON radice in entrambi i casi.

Nel caso di un DII, inoltre, è necessario prendere in considerazione gli elementi seguenti:

- Alcuni elementi nell'elenco [figli] non devono essere presenti. Non fare affidamento su tale situazione in caso di lettura di XML mappato da JSON.

- L'elenco [figli] non contiene voci di informazioni di commento.

- L'elenco [figli] non contiene voci di informazioni DTD.

- L'elenco [figli] non contiene informazioni personali `<?xml…>` (PI) (la dichiarazione non è considerata un elemento di informazioni PI)

- Il set [notazioni] è vuoto.

- Il set [entità non analizzate] è vuoto.

Esempio: nel documento seguente non è contenuto alcun mapping a JSON perché [figli] contiene una PI e un commento.

```xml
<?xml version="1.0"?>
<!--comment--><?pi?>
<root type="number">42</root>
```

L'EII per l'Elemento JSON radice ha le caratteristiche seguenti:

- [nome locale] ha il valore "root".

- [nome dello spazio dei nomi] non ha valore.

- [prefisso] non ha valore.

- [figli] può contenere EII (che rappresentano elementi interni come descritto più avanti) o CII (Character Information Items come descritto più avanti) o nessuno dei due, ma non entrambi.

- [attributi] può contenere le voci di informazioni sugli attributi facoltativi seguenti (AII)

- L'attributo di tipo JSON ("type") come descritto più avanti. Questo attributo è utilizzato per mantenere il tipo JSON (stringa, numero, booleano, oggetto, matrice o null) nell'XML di cui è stato eseguito il mapping.

- L'attributo nome\_\_del contratto dati (" tipo") come descritto più avanti. Questo attributo può essere presente solo se è presente anche l'attributo del tipo JSON e il suo [valore normalizzato] è "object". Questo attributo è utilizzato da `DataContractJsonSerializer` per mantenere informazioni sul tipo di contratto dati , ad esempio, nei casi polimorfici in cui viene serializzato un tipo derivato ed è previsto un tipo di base. Se non si utilizza `DataContractJsonSerializer`, nella maggior parte dei casi questo attributo viene ignorato.

- [spazi dei nomi nell'ambito] contiene l'associazione di "xml" a `http://www.w3.org/XML/1998/namespace` come richiesto dalla specifica dell'infoset.

- [figli], [attributi] e [spazi dei nomi nell'ambito] non devono avere altri elementi tranne quelli specificati in precedenza e [attributi dello spazio dei nomi] non deve avere membri, ma non fare affidamento su questa situazione in caso di lettura di XML mappato da JSON.

Esempio: nel documento seguente non è presente alcun mapping a JSON perché [attributi dello spazio dei nomi] non è vuoto.

```xml
<?xml version="1.0"?>
<root xmlns:a="myattributevalue">42</root>
```

L'AII per l'attributo del tipo JSON ha le caratteristiche seguenti:

- [nome dello spazio dei nomi] non ha valore.
- [prefisso] non ha valore.
- [nome locale] è "type".
- [valore normalizzato] è uno dei possibili valori del tipo descritto nella sezione seguente.
- [specificato] è `true`.
- [tipo attributo] non ha valore.
- [riferimenti] non ha valore.

L'AII per l'attributo del nome del contratto dati ha le caratteristiche seguenti:

- [nome dello spazio dei nomi] non ha valore.
- [prefisso] non ha valore.
- [nome locale]\_\_è " type" (due caratteri di sottolineatura e poi "tipo").
- [valore normalizzato] è qualsiasi stringa Unicode valida, il mapping di questa stringa a JSON viene descritto nella sezione seguente.
- [specificato] è `true`.
- [tipo attributo] non ha valore.
- [riferimenti] non ha valore.

Gli elementi interni contenuti all'interno dell'Elemento JSON radice o altri elementi interni hanno le caratteristiche seguenti:

- [nome locale] può avere qualsiasi valore come descritto più avanti.
- [nome dello spazio dei nomi], [prefisso], [figli], [attributi], [attributi dello spazio dei nomi] e [spazi dei nomi nell'ambito] sono soggetti alle stesse regole dell'Elemento JSON radice.

Sia nell'Elemento JSON radice che negli elementi interni, l'attributo del tipo JSON definisce il mapping a JSON, i [figli] possibili e la loro interpretazione. [valore normalizzato] dell'attributo fa distinzione tra maiuscole e minuscole e deve essere minuscolo e non può contenere spazi vuoti.

|[valore normalizzato] dell'IAA dell'attributo di tipo JSON|[figli] consentiti dell'EII corrispondente|Mapping a JSON|
|---------------------------------------------------------|---------------------------------------------------|---------------------|
|`string` (o assenza dell'AII del tipo JSON)<br /><br /> Una `string` e l'assenza dell'AII del tipo JSON sono la stessa cosa e creano l'elemento predefinito `string`.<br /><br /> Pertanto, `<root> string1</root>``string` esegue il mapping alla  "string1" JSON.|0 o più CII|Oggetto `string` JSON (JSON RFC, sezione 2.5). Ogni `char` è un carattere che corrisponde al [character code] di CII. Se non sono presenti CII, esegue il mapping a una `string` JSON vuota.<br /><br /> Esempio: l'elemento seguente viene mappato a un frammento JSON:<br /><br /> `<root type="string">42</root>`<br /><br /> Il frammento JSON è "42".<br /><br /> Nel mapping da XML a JSON, i caratteri che devono essere preceduti dal carattere di escape vengono mappati ai caratteri di escape, tutti gli altri vengono mappati a caratteri non di escape. Il carattere "/" è speciale: viene eseguito il escape anche\\se non deve essere (scritto come " /").<br /><br /> Esempio: l'elemento seguente viene mappato a un frammento JSON.<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> Il frammento JSON \\è\\"da\\/ta "".<br /><br /> Nel mapping da JSON a XML, qualsiasi carattere preceduto o no da un carattere di escape viene mappato correttamente al [codice carattere] corrispondente.<br /><br /> Esempio: il frammento JSON "\u0041BC" viene mappato all'elemento XML seguente.<br /><br /> `<root type="string">ABC</root>`<br /><br /> La stringa può essere racchiusa in uno spazio vuoto ('ws' nella sezione 2 della RFC JSON) che non viene mappato a XML.<br /><br /> Esempio: il frammento JSON            "ABC", (sono presenti spazi prima delle doppie virgolette di apertura) viene mappato all'elemento XML seguente.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Qualsiasi spazio vuoto in XML viene mappato a uno spazio vuoto in JSON.<br /><br /> Esempio: l'elemento XML seguente viene mappato a un frammento JSON.<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> Il frammento JSON è " A BC ".|
|`number`|1 o più CII|Un `number` JSON (JSON RFC, sezione 2.4), probabilmente circondato da spazi vuoti. Ogni carattere nella combinazione numero/spazio vuoto è un carattere che corrisponde al [codice carattere] dal CII.<br /><br /> Esempio: l'elemento seguente viene mappato a un frammento JSON.<br /><br /> `<root type="number">    42</root>`<br /><br /> Il frammento JSON è    42<br /><br /> (Lo spazio vuoto viene mantenuto).|
|`boolean`|4 o 5 CII `true` (che corrisponde a o `false`), eventualmente circondate da CII di spazi bianchi aggiuntivi.|Una sequenza di CII che corrisponde alla stringa "true" viene mappata al valore letterale `true` e la sequenza di CII che corrisponde alla stringa "false" viene mappata al valore letterale `false`. Lo spazio bianco circostante viene conservato.<br /><br /> Esempio: l'elemento seguente viene mappato a un frammento JSON.<br /><br /> `<root type="boolean"> false</root>`<br /><br /> Il frammento JSON è `false`.|
|`null`|Nessuno consentito.|Il valore letterale `null`. Nel mapping JSON a `null` XML, il può essere circondato da uno spazio vuoto ('ws' nella sezione 2) che non viene mappato a XML.<br /><br /> Esempio: l'elemento seguente viene mappato a un frammento JSON.<br /><br /> `<root type="null"/>`<br /><br /> o<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> In entrambi i casi il frammento JSON è `Null`.|
|`object`|0 o più EII.|`begin-object` (parentesi graffa aperta) come nella sezione 2.2 di JSON RFC, seguito da un record del membro per ogni EII come descritto più avanti. Se esiste più di un EII, sono presenti separatori di valore (virgole) tra il record dei membri. Tutto è seguito da un fine oggetto (parentesi graffa chiusa).<br /><br /> Esempio: l'elemento seguente viene mappato al frammento JSON.<br /><br /> `<root type="object">`<br /><br /> `<type1 type="string">aaa\</type1>`<br /><br /> `<type2 type="string">bbb\</type2>`<br /><br /> `</root >`<br /><br /> Il frammento JSON è `{"type1":"aaa","type2":"bbb"}`.<br /><br /> Se nel mapping da XML a JSON è presente l'attributo tipo di contratto dati, all'inizio viene inserito un record del membro aggiuntivo. Il nome è il [nome locale] dell'attributo del tipo di contratto dati ("\_\_tipo") e il relativo valore è [valore normalizzato] dell'attributo. Al contrario, nel mapping json a XML, se il nome del primo record del membro è il\_\_[nome locale] dell'attributo del tipo di contratto dati (ovvero " tipo"), un attributo del tipo di contratto dati corrispondente è presente nell'XML mappato, ma non è presente un EII corrispondente. Si noti che, perché questo mapping speciale si applichi, il record del membro deve essere per primo nell'oggetto JSON. Ciò si discosta dall'elaborazione JSON abituale, in cui l'ordine dei record dei membri non è importante.<br /><br /> Esempio:<br /><br /> il frammento JSON seguente viene mappato a XML.<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> L'XML è il codice seguente.<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> Si noti che \_ \_il tipo AII \_ \_è presente, ma non è presente alcun tipo EII.<br /><br /> Se, tuttavia, l'ordine in JSON è invertito come illustrato nell'esempio seguente.<br /><br /> `{"name":"John","\_\_type":"Person"}`<br /><br /> Viene illustrato l'XML corrispondente.<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> Cioè, \__type cessa di avere un significato speciale e le mappe di un EII come al solito, non AII.<br /><br /> Le regole sull'utilizzo o meno di caratteri di escape per il [valore normalizzato] di AII quando mappato a un valore JSON sono identiche a quelle per le stringhe JSON, come specificato nella riga "string" di questa tabella.<br /><br /> Esempio:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> all'esempio precedente può essere mappato al JSON seguente.<br /><br /> `{"__type":"\\abc"}`<br /><br /> In un mapping da XML a JSON, il primo nome [locale] dell'Interfaccia di Web Ai deve essere "\_\_type".<br /><br /> Gli spazi`ws`vuoti ( ) non vengono mai generati in XML per il mapping JSON per gli oggetti e vengono ignorati nel mapping JSON a XML.<br /><br /> Esempio: il frammento JASON seguente viene mappato a un elemento XML.<br /><br /> `{ "ccc" : "aaa", "ddd" :"bbb"}`<br /><br /> Nel codice seguente viene illustrato l'elemento XML.<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|
|array|0 o più EII|Un inizio di matrice (parentesi quadra aperta) come nella sezione 2.3 di JSON RFC, seguita da un record della matrice per ogni EII come descritto più avanti. Se esiste più di un EII, sono presenti separatori di valore (virgole) tra i record delle matrici. Il tutto, è seguito da un fine matrice.<br /><br /> Esempio: l'elemento XML seguente viene mappato a un frammento JSON.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> Il frammento JSON è`["aaa","bbb"]`<br /><br /> Gli spazi`ws`vuoti ( ) non vengono mai generati in XML per il mapping JSON per le matrici e vengono ignorati nel mapping JSON a XML.<br /><br /> Esempio: un frammento JSON.<br /><br />`["aaa", "bbb"]`<br /><br /> L'elemento XML su cui viene eseguito il mapping.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|

I record dei membri funzionano come segue:

- Il [nome locale] dell'elemento interno viene mappato alla parte `string` di `member`, come definito nella sezione 2.2 di JSON RFC.

Esempio: l'elemento seguente viene mappato a un frammento JSON.

```xml
<root type="object">
    <myLocalName type="string">aaa</myLocalName>
</root>
```

Viene visualizzato il frammento JSON seguente.

```json
{"myLocalName":"aaa"}
```

- Nel mapping da XML a JSON, i caratteri che devono essere preceduti dal carattere di escape in JSON sono preceduti dal carattere di escape, gli altri no. Il carattere "/",viene preceduto da un carattere di escape anche se ciò non è necessario (non richiede il carattere di escape nel mapping da JSON a XML). Ciò è necessario per supportare il formato ASP.NET AJAX per i dati `DateTime` in JSON.

- Nel mapping da JSON a XML, vengono presi tutti i caratteri (compresi quelli senza carattere di escape, se necessario) per formare una `string` che produce un [nome locale].

- I [figli] dell'elemento interno vengono mappati al valore nella sezione 2.2, secondo `JSON Type Attribute` come per `Root JSON Element`. Sono consentiti più livelli di annidamento di EII (incluso l'annidamento all'interno di matrici).

Esempio: l'elemento seguente viene mappato a un frammento JSON.

```xml
<root type="object">
    <myLocalName1 type="string">myValue1</myLocalName1>
    <myLocalName2 type="number">2</myLocalName2>
    <myLocalName3 type="object">
        <myNestedName1 type="boolean">true</myNestedName1>
        <myNestedName2 type="null"/>
    </myLocalName3>
</root >
```

Viene mappato al frammento JSON seguente.

```json
{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}
```

> [!NOTE]
> Nel mapping precedente non esiste alcun passaggio di codifica XML. Pertanto, WCF supporta solo i documenti JSON in cui tutti i caratteri nei nomi di chiave sono caratteri validi nei nomi degli elementi XML. Ad esempio, il documento JSON "<":"a" non è supportato perché < non è un nome valido per un elemento XML.

La situazione inversa (caratteri validi in XML ma non in JSON) non causa alcun problema perché il mapping precedente include passaggi con/senza caratteri di escape in JSON.

I record di matrici funzionano come segue:

- Il [nome locale] dell'elemento interno è "item".

- I [figli] dell'elemento interno vengono mappati al valore nella sezione 2.3, secondo l'attributo Type di JSON così come per l'elemento JSON radice. Sono consentiti più livelli di annidamento di EII (incluso l'annidamento all'interno di oggetti).

Esempio: l'elemento seguente viene mappato a un frammento JSON.

```xml
<root type="array">
    <item type="string">myValue1</item>
    <item type="number">2</item>
    <item type="array">
    <item type="boolean">true</item>
    <item type="null"/></item>
</root>
```

Quello che segue è il frammento JSON.

```json
["myValue1",2,[true,null]]
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>
- [Serializzazione JSON autonoma](stand-alone-json-serialization.md)
