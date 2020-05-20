---
title: Convalida basata sul metodo push di XmlSchemaValidator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: d5b2fe4325000023acc98580a2a6d014f56fecbd
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419109"
---
# <a name="xmlschemavalidator-push-based-validation"></a>Convalida basata sul metodo push di XmlSchemaValidator

La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce un meccanismo efficiente e a elevate prestazioni per la convalida basata sul metodo push di dati XML in base a schemi XML. Ad esempio, la classe <xref:System.Xml.Schema.XmlSchemaValidator> consente di convalidare un infoset XML sul posto senza la necessità di serializzarlo come documento XML e di eseguire nuovamente l'analisi del documento mediante un lettore XML di convalida.

La classe <xref:System.Xml.Schema.XmlSchemaValidator> può essere usata in scenari avanzati, ad esempio per la compilazione di motori di convalida in base a origini dati XML personalizzate oppure per la compilazione di un writer XML di convalida.

Di seguito è riportato un esempio di utilizzo della classe <xref:System.Xml.Schema.XmlSchemaValidator> per convalidare il file `contosoBooks.xml` in base allo schema `contosoBooks.xsd`. Nell'esempio viene usata la classe <xref:System.Xml.Serialization.XmlSerializer> per deserializzare il file `contosoBooks.xml` e passare il valore dei nodi ai metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator>.

> [!NOTE]
> Questo esempio viene usato in tutte le sezioni di questo argomento.

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

Nell'esempio il file `contosoBooks.xml` viene considerato come input.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

Anche il file `contosoBooks.xsd` viene considerato come input.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a>Convalida di dati XML mediante XmlSchemaValidator

Per iniziare la convalida di un infoset XML, è necessario innanzitutto inizializzare una nuova istanza della classe <xref:System.Xml.Schema.XmlSchemaValidator> usando il costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.

Il costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> accetta gli oggetti <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, <xref:System.Xml.XmlNamespaceManager> e un valore <xref:System.Xml.Schema.XmlSchemaValidationFlags> come parametri. L'oggetto <xref:System.Xml.XmlNameTable> viene usato per atomizzare stringhe note di spazi dei nomi, quali lo spazio dei nomi dello schema, lo spazio dei nomi XML e così via. Tale oggetto viene passato al metodo <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> durante la convalida del contenuto semplice. Nell'oggetto <xref:System.Xml.Schema.XmlSchemaSet> sono contenuti gli schemi XML usato per convalidare l'infoset XML. L'oggetto <xref:System.Xml.XmlNamespaceManager> viene usato per risolvere gli spazi dei nomi rilevati durante la convalida. Il valore <xref:System.Xml.Schema.XmlSchemaValidationFlags> viene usato per disabilitare determinate funzionalità di convalida.

Per altre informazioni sul costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="initializing-validation"></a>Inizializzazione della convalida

Dopo la creazione di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator>, sono disponibili due metodi di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> usati per inizializzare lo stato dell'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>. Di seguito sono riportati i due metodi <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> predefinito consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale e il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale per la convalida parziale.

È possibile chiamare i metodi <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> solo dopo la creazione di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> o la chiamata al metodo <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.

Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, vedere l'introduzione. Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="partial-validation"></a>Convalida parziale

Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro consente di inizializzare un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> al relativo stato iniziale per la convalida parziale.

Nell'esempio seguente un tipo <xref:System.Xml.Schema.XmlSchemaObject> viene inizializzato per la convalida parziale usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>. L'elemento dello schema `orderNumber` viene passato selezionandolo in base al tipo <xref:System.Xml.XmlQualifiedName> nella raccolta <xref:System.Xml.Schema.XmlSchemaObjectTable> restituita dalla proprietà <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> dell'oggetto <xref:System.Xml.Schema.XmlSchemaSet>. Questo elemento specifico viene quindi convalidato dall'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

Nell'esempio il seguente schema XML viene considerato come input.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="adding-additional-schemas"></a>Aggiunta di altri schemi

Per aggiungere uno schema XML al set di schemi usato durante la convalida, viene usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator>. Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> può essere usato per simulare l'effetto prodotto dal rilevamento di uno schema XML inline nell'infoset XML da convalidare.

> [!NOTE]
> Lo spazio dei nomi di destinazione del parametro <xref:System.Xml.Schema.XmlSchema> non può corrispondere ad alcun elemento o attributo già rilevato dall'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.
>
> Se il valore <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> non è stato passato come parametro al costruttore <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> non esegue alcuna operazione.

Il risultato del metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> dipende dal contesto corrente del nodo XML da convalidare. Per altre informazioni sui contesti di convalida, vedere la sezione "Contesto di convalida" in questo argomento.

Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="validating-elements-attributes-and-content"></a>Convalida di elementi, attributi e contenuto

La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce diversi metodi usati per convalidare elementi, attributi e contenuto in un infoset XML in base a schemi XML. Nella tabella seguente viene descritto ciascuno di questi metodi.

|Metodo|Descrizione|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Convalida il nome dell'elemento nel contesto corrente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Convalida l'attributo nel contesto dell'elemento corrente oppure in base all'oggetto <xref:System.Xml.Schema.XmlSchemaAttribute> passato come parametro al metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|Verifica la presenza di tutti gli attributi richiesti nel contesto dell'elemento e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto figlio dell'elemento.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Verifica se il testo è consentito nel contesto dell'elemento corrente e accumula il testo da convalidare se l'elemento corrente dispone di contenuto semplice.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Verifica se gli spazi vuoti sono consentiti nel contesto dell'elemento corrente e accumula gli spazi vuoti da convalidare se l'elemento corrente dispone di contenuto semplice.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Verifica se il contenuto di testo dell'elemento è valido in base al relativo tipo di dati per gli elementi con contenuto semplice e verifica se il contenuto dell'elemento corrente è completo per gli elementi con contenuto complesso.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Ignora la convalida del contenuto dell'elemento corrente e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto nel contesto dell'elemento padre.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Termina la convalida e verifica i vincoli di identità per l'intero documento XML se è impostata l'opzione di convalida <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.|

> [!NOTE]
> La classe <xref:System.Xml.Schema.XmlSchemaValidator> presenta una transizione dello stato definita che impone la sequenza e l'occorrenza delle chiamate effettuate a ciascuno dei metodi descritti nella tabella precedente. La transizione dello stato specifica per la classe <xref:System.Xml.Schema.XmlSchemaValidator> è descritta nella sezione "Transizione dello stato di XmlSchemaValidator" di questo argomento.

Per un esempio dei metodi usati per convalidare elementi, attributi e contenuto di un infoset XML, vedere l'esempio nella sezione precedente. Per altre informazioni su questi metodi, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="validating-content-using-an-xmlvaluegetter"></a>Convalida del contenuto mediante XmlValueGetter

Il <xref:System.Xml.Schema.XmlValueGetter>`delegate` può essere usato per passare il valore di nodi Attribute, di nodi di tipo text o di nodi con spazi vuoti come tipi CLR (Common Language Runtime) compatibili con il tipo XSD (XML Schema Definition Language) del nodo Attribute, di tipo text o con spazi vuoti. Un <xref:System.Xml.Schema.XmlValueGetter>`delegate` è utile se il valore CLR di un nodo Attribute, di un nodo di tipo text o di un nodo con spazi vuoti è già disponibile. Inoltre, evita la necessità di convertire il nodo in `string` e di analizzarlo nuovamente per la convalida.

I metodi di overload <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> accettano il valore dei nodi Attribute, dei nodi di tipo text o dei nodi con spazi vuoti come `string` o come <xref:System.Xml.Schema.XmlValueGetter>`delegate`.

I seguenti metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> accettano un tipo <xref:System.Xml.Schema.XmlValueGetter>`delegate` come parametro.

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

Di seguito è riportato un <xref:System.Xml.Schema.XmlValueGetter>`delegate` di esempio descritto nell'esempio della classe <xref:System.Xml.Schema.XmlSchemaValidator> nell'introduzione. Il <xref:System.Xml.Schema.XmlValueGetter>`delegate` restituisce il valore di un attributo come oggetto <xref:System.DateTime>. Per convalidare l'oggetto <xref:System.DateTime> restituito dall'oggetto <xref:System.Xml.Schema.XmlValueGetter>, l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> lo converte innanzitutto in ValueType (ovvero nel mapping predefinito di CLR per il tipo XSD) per il tipo di dati dell'attributo, quindi verifica i facet nel valore convertito.

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

Per un esempio completo dell'oggetto <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vedere l'introduzione. Per altre informazioni sul <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vedere la documentazione di riferimento per il tipo <xref:System.Xml.Schema.XmlValueGetter> e per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="post-schema-validation-information"></a>informazioni sulla convalida post-schema

La classe <xref:System.Xml.Schema.XmlSchemaInfo> rappresenta alcune delle informazioni di convalida post-schema di un nodo XML convalidata dalla classe <xref:System.Xml.Schema.XmlSchemaValidator>. Diversi metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> accettano un oggetto <xref:System.Xml.Schema.XmlSchemaInfo> come parametro `null` (`out`) facoltativo.

Una volta eseguita la convalida, le proprietà dell'oggetto <xref:System.Xml.Schema.XmlSchemaInfo> vengono impostate con i risultati della convalida. Ad esempio, dopo la convalida di un attributo usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, le proprietà <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> e <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> dell'oggetto <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A>, se specificate, vengono impostate con i risultati della convalida.

Il seguente metodo della classe <xref:System.Xml.Schema.XmlSchemaValidator> accetta un oggetto <xref:System.Xml.Schema.XmlSchemaInfo> come parametro out.

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

Per un esempio completo della classe <xref:System.Xml.Schema.XmlSchemaInfo>, vedere l'introduzione. Per altre informazioni sulla classe <xref:System.Xml.Schema.XmlSchemaInfo>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaInfo>.

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a>Recupero di particelle e attributi previsti e di attributi predefiniti non specificati

La classe <xref:System.Xml.Schema.XmlSchemaValidator> fornisce i metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> per il recupero di particelle e attributi previsti e di attributi predefiniti non specificati nel contesto di convalida corrente.

#### <a name="retrieving-expected-particles"></a>Recupero di particelle previste

Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice di oggetti <xref:System.Xml.Schema.XmlSchemaParticle> contenenti le particelle previste nel contesto dell'elemento corrente. Le particelle valide che possono essere restituite dal metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> sono istanze delle classi <xref:System.Xml.Schema.XmlSchemaElement> e <xref:System.Xml.Schema.XmlSchemaAny>.

Se il compositor per il modello di contenuto è `xs:sequence`, verrà restituita solo la particella successiva nella sequenza. Se il compositor per il modello di contenuto è `xs:all` o `xs:choice`, verranno restituite tutte le particelle che possono seguire nel contesto dell'elemento corrente.

> [!NOTE]
> Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato subito dopo il metodo <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà tutti gli elementi globali.

Ad esempio, nello schema XSD (XML Schema Definition Language) e nel documento XML seguenti, dopo la convalida dell'elemento `book`, l'elemento `book` è il contesto dell'elemento corrente. Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaElement> che rappresenta l'elemento `title`. Se il contesto di convalida è l'elemento `title`, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce una matrice vuota. Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato dopo la convalida dell'elemento `title` ma prima della convalida dell'elemento `description`, restituirà una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaElement> che rappresenta l'elemento `description`. Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> viene chiamato dopo la convalida dell'elemento `description`, restituirà una matrice contenente un singolo oggetto <xref:System.Xml.Schema.XmlSchemaAny> che rappresenta il carattere jolly.

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 Nell'esempio viene preso come input il codice XML seguente:

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

Nell'esempio il seguente schema XSD viene preso come input:

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare. Per altre informazioni, vedere la sezione "Contesto di convalida" in questo argomento.

Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vedere l'introduzione. Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-expected-attributes"></a>Recupero di attributi previsti

Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce una matrice di oggetti <xref:System.Xml.Schema.XmlSchemaAttribute> contenenti gli attributi previsti nel contesto dell'elemento corrente.

Ad esempio, nell'esempio dell'introduzione il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene usato per recuperare tutti gli attributi dell'elemento `book`.

Se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene chiamato subito dopo il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, verranno restituiti tutti gli attributi che possono essere presenti nel documento XML. Tuttavia, se il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> viene chiamato dopo una o più chiamate al metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, verranno restituiti gli attributi che non sono ancora stati convalidati per l'elemento corrente.

> [!NOTE]
> I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare. Per altre informazioni, vedere la sezione "Contesto di convalida" in questo argomento.

Per un esempio del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vedere l'introduzione. Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-unspecified-default-attributes"></a>Recupero di attributi predefiniti non specificati

Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> compila il tipo <xref:System.Collections.ArrayList> specificato con gli oggetti <xref:System.Xml.Schema.XmlSchemaAttribute> per gli attributi con valori predefiniti che non sono stati convalidati in precedenza usando il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> nel contesto dell'elemento. Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> deve essere chiamato dopo aver chiamato il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> in ogni attributo del contesto dell'elemento. Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> deve essere usato per determinare gli attributi predefiniti da inserire nel documento XML da convalidare, è necessario usare .

Per altre informazioni sul metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="handling-schema-validation-events"></a>Gestione degli eventi di convalida dello schema

Gli avvisi e gli errori di convalida dello schema rilevati durante la convalida sono gestiti dall'evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> della classe <xref:System.Xml.Schema.XmlSchemaValidator>.

Gli avvisi di convalida dello schema presentano un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Warning> mentre gli errori di convalida dello schema presentano un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Error>. Se non è stato assegnato alcun evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>, verrà generato un tipo <xref:System.Xml.Schema.XmlSchemaValidationException> per tutti gli errori di convalida dello schema con un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Error>. Tuttavia, non verrà generato un tipo <xref:System.Xml.Schema.XmlSchemaValidationException> per gli avvisi di convalida dello schema con un valore <xref:System.Xml.Schema.XmlSeverityType> pari a <xref:System.Xml.Schema.XmlSeverityType.Warning>.

Di seguito è riportato un esempio di un ti<xref:System.Xml.Schema.ValidationEventHandler> che riceve avvisi ed errori di convalida dello schema rilevati durante la convalida dello schema nell'esempio dell'introduzione.

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

Per un esempio completo del tipo <xref:System.Xml.Schema.ValidationEventHandler>, vedere l'introduzione. Per altre informazioni, vedere la documentazione di riferimento per la classe <xref:System.Xml.Schema.XmlSchemaInfo>.

## <a name="xmlschemavalidator-state-transition"></a>Transizione dello stato di XmlSchemaValidator

La classe <xref:System.Xml.Schema.XmlSchemaValidator> presenta una transizione dello stato definita che impone la sequenza e l'occorrenza delle chiamate effettuate a ciascuno dei metodi usati per convalidare elementi, attributi e contenuto di un infoset XML.

Nella tabella seguente vengono descritti la transizione dello stato della classe <xref:System.Xml.Schema.XmlSchemaValidator>, nonché la sequenza e l'occorrenza delle chiamate del metodo che possono essere effettuate in ciascuno stato.

|State|Transizione|
|-----------|----------------|
|Validate|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|
|TopLevel|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|
|Elemento|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* ( <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Contenuto \* )? <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A><xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> &#124; di contenuto \* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|
|Contenuto|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|

> [!NOTE]
> Se la chiamata al metodo non viene effettuata nella sequenza corretta in base allo stato corrente di un oggetto <xref:System.InvalidOperationException>, verrà generato un oggetto <xref:System.Xml.Schema.XmlSchemaValidator> da parte di ciascuno dei metodi della tabella precedente.

Nella tabella precedente, relativa alla transizione dello stato, vengono usati i segni di punteggiatura per descrivere i metodi e alti stati che possono essere chiamati per ciascuno stato di transizione della classe <xref:System.Xml.Schema.XmlSchemaValidator>. I segni usati sono gli stessi del riferimento agli standard XML per la DTD (Document Type Definition).

Nella tabella seguente vengono descritti gli effetti dei segni di punteggiatura della tabella precedente relativa alla transizione dello stato sui metodi e su altri stati che possono essere chiamati per ciascuno stato di transizione della classe <xref:System.Xml.Schema.XmlSchemaValidator>.

|Simbolo|Descrizione|
|------------|-----------------|
|&#124;|È possibile chiamare il metodo o lo stato che precede o che segue la barra.|
|?|Il metodo o lo stato che precede il punto interrogativo è facoltativo. Tuttavia, se viene chiamato, può essere chiamato solo una volta.|
|\*|Il metodo o lo stato che precede il \* simbolo è facoltativo e può essere chiamato più di una volta.|

## <a name="validation-context"></a>Contesto di convalida

I metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> usati per convalidare elementi, attributi e contenuto in un infoset XML modificano il contesto di convalida di un oggetto <xref:System.Xml.Schema.XmlSchemaValidator>. Ad esempio, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> ignora la convalida del contenuto dell'elemento corrente e prepara l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> per la convalida del contenuto nel contesto dell'elemento padre. Dal punto di vista funzionale, equivale a ignorare la convalida di tutti gli elementi figlio dell'elemento corrente e a chiamare il metodo <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.

I risultati dei metodi <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> e <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> della classe <xref:System.Xml.Schema.XmlSchemaValidator> dipendono dal contesto corrente da convalidare.

Nella tabella seguente vengono descritti i risultati della chiamata di questi metodi dopo aver chiamato uno dei metodi della classe <xref:System.Xml.Schema.XmlSchemaValidator> usata per convalidare elementi, attributi e contenuto di un insieme di informazioni XML.

|Metodo|GetExpectedParticles|GetExpectedAttributes|AddSchema|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|Se viene chiamato il metodo predefinito <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice contenente tutti gli elementi globali.<br /><br /> Se il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro viene chiamato per inizializzare la convalida parziale di un elemento, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà solo l'elemento con cui viene inizializzato l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.|Se viene chiamato il metodo predefinito <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.<br /><br /> Se il metodo di overload <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> che accetta un tipo <xref:System.Xml.Schema.XmlSchemaObject> come parametro viene chiamato per inizializzare la convalida parziale di un attributo, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà solo l'attributo con cui viene inizializzato l'oggetto <xref:System.Xml.Schema.XmlSchemaValidator>.|Aggiunge lo schema al tipo <xref:System.Xml.Schema.XmlSchemaSet> dell'oggetto <xref:System.Xml.Schema.XmlSchemaValidator> se non si verificano errori di pre-elaborazione.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Se l'elemento di contesto è valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista come elementi figlio dell'elemento di contesto.<br /><br /> Se l'elemento di contesto è non valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.|Se l'elemento di contesto è valido e se non è stata effettuata in precedenza alcuna chiamata a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco di tutti gli attributi definiti nell'elemento di contesto.<br /><br /> Se alcuni attributi sono già stati convalidati, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco degli attributi rimanenti da convalidare.<br /><br /> Se l'elemento di contesto è non valido, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Se l'attributo di contesto è un attributo di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.<br /><br /> In caso contrario, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.|Se l'attributo di contesto è un attributo di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.<br /><br /> In caso contrario, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà l'elenco degli attributi rimanenti da convalidare.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.|Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi obbligatori e facoltativi che devono ancora essere convalidati per l'elemento di contesto.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista come primo elemento figlio dell'elemento di contesto.|Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce una matrice vuota.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Se contentType dell'elemento di contesto è Mixed, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista nella posizione successiva.<br /><br /> Se contentType dell'elemento di contesto è TextOnly o Empty, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.<br /><br /> Se contentType dell'elemento di contesto è ElementOnly, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà la sequenza di elementi prevista nella posizione successiva. Tuttavia, si è già verificato un errore di convalida.|Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi non convalidati per l'elemento di contesto.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Se lo spazio vuoto di contesto è uno spazio vuoto di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituirà una matrice vuota.<br /><br /> In caso contrario, il comportamento del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> sarà lo stesso di <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Se lo spazio vuoto di contesto è uno spazio vuoto di primo livello, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà una matrice vuota.<br /><br /> In caso contrario, il comportamento del metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> sarà lo stesso di <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> restituisce la sequenza di elementi prevista dopo l'elemento di contesto, ovvero gli eventuali elementi di pari livello.|Il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituisce un elenco degli attributi non convalidati per l'elemento di contesto.<br /><br /> Se l'elemento di contesto non presenta un elemento padre, il metodo <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> restituirà un elenco vuoto. L'elemento di contesto è l'elemento padre dell'elemento corrente in cui è stato chiamato <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Come per <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Come per <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Come sopra.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Restituisce una matrice vuota.|Restituisce una matrice vuota.|Come sopra.|

> [!NOTE]
> La chiamata dei metodi descritti nella tabella precedente non influisce sul valore restituito dalle diverse proprietà della classe <xref:System.Xml.Schema.XmlSchemaValidator>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Schema.XmlSchemaValidator>
