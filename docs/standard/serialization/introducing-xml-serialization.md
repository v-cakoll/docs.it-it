---
title: Dettagli della serializzazione XMLDetails of XML serialization
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, about XML serialization
- ICollection interface, serializing
- XmlSerializer class, serializing
- serialization, about serialization
- DataSet class, serializing
- XML Schema, serializing
ms.assetid: 8c63200d-db63-4a03-a93d-21641623df62
ms.openlocfilehash: d644e80cbf5ac17fca4df039d915c847a1936217
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588451"
---
# <a name="xml-serialization"></a>serializzazione XML

La serializzazione è il processo di conversione di un oggetto in un formato che può essere agevolmente trasportato. Ad esempio, è possibile serializzare un oggetto e trasferirlo via Internet tramite protocollo HTTP tra un client e un server. Viceversa, la deserializzazione ricostruisce l'oggetto dal flusso.

 La serializzazione XML serializza solo i campi pubblici e i valori di proprietà di un oggetto in un flusso XML. La serializzazione XML non include informazioni sul tipo. Ad esempio, se un oggetto **Book** è incluso nello spazio dei nomi **Library**, non vi è alcuna garanzia che venga deserializzato in un oggetto dello stesso tipo.

> [!NOTE]
> La serializzazione XML non converte metodi, indicizzatori o proprietà in sola lettura (salvo le raccolte in sola lettura). Per serializzare tutti i campi e le proprietà di un oggetto, pubblici e privati, utilizzare <xref:System.Runtime.Serialization.DataContractSerializer> invece della serializzazione XML.

 La classe centrale nella serializzazione XML è la classe <xref:System.Xml.Serialization.XmlSerializer> e i metodi più importanti in questa classe sono i metodi **Serialize** e **Deserialize**. La classe <xref:System.Xml.Serialization.XmlSerializer> crea file C# e li compila in file dll per eseguire tale serializzazione. In .NET Framework 2.0 lo [strumento per la generazione di serializzatori XML (Sgen.exe)](xml-serializer-generator-tool-sgen-exe.md) è progettato per generare in anticipo questi assembly di serializzazione perché vengano distribuiti con l'applicazione, in modo da migliorare le prestazioni di avvio. Il flusso XML generato da **XmlSerializer** è conforme alla [raccomandazione XSD (XML Schema Definition Language) 1.0](https://www.w3.org/TR/xslt)del World Wide Web Consortium (W3C). Inoltre, i tipi di dati generati sono conformi al documento intitolato "XML Schema Part 2: Datatypes".

 I dati negli oggetti vengono descritti tramite costrutti del linguaggio di programmazione come classi, campi, proprietà, tipi primitivi, matrici e anche XML incorporato sotto forma di oggetti **XmlElement** o **XmlAttribute**. È possibile creare le classi, annotate con attributi, o utilizzare lo strumento XML Schema Definition per generare le classi basate su uno schema XML esistente.

 Se si dispone di uno schema XML, è possibile eseguire lo strumento XML Schema Definition per generare un set di classi fortemente tipizzate rispetto allo schema e annotate con attributi. Quando viene serializzata un'istanza di tale classe, l'XML generato è conforme allo schema XML. Con l'utilizzo di tale classe, è possibile effettuare la programmazione rispetto a un modello a oggetti facilmente modificato essendo certi che l'XML generato sia conforme allo schema XML. Si tratta di un'alternativa all'uso di altre classi in .NET Framework, ad esempio le classi **XmlReader** e **XmlWriter**, per analizzare e scrivere un flusso XML. Per altre informazioni, vedere [XML Documents and Data](../../../docs/standard/data/xml/index.md) (Documenti e dati XML). Queste classi consentono di analizzare qualsiasi flusso XML. Al contrario, usare **XmlSerializer** quando si prevede che il flusso XML sarà conforme a un oggetto XML Schema noto.

 Gli attributi controllano il flusso XML generato dalla classe **XmlSerializer**, consentendo di impostare lo spazio dei nomi XML, il nome dell'elemento, il nome di attributo e altre voci per il flusso XML. Per altre informazioni su questi attributi e sul modo in cui controllano la serializzazione XML, vedere [Controllo della serializzazione XML mediante attributi](controlling-xml-serialization-using-attributes.md). Per una tabella degli attributi usati per controllare l'XML generato, vedere [Attributi per il controllo della serializzazione XML](attributes-that-control-xml-serialization.md).

 La classe **XmlSerializer** può serializzare ulteriormente un oggetto e può generare un flusso XML SOAP codificato. L'elemento XML generato risulta conforme alla sezione 5 del documento "Simple Object Access Protocol (SOAP) 1.1" del World Wide Web Consortium. Per altre informazioni su questo processo, vedere [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md). Per una tabella degli attributi che controllano l'XML generato, vedere [Attributi per il controllo della serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).

 La classe **XmlSerializer** genera i messaggi SOAP creati dai e passati ai servizi Web XML. Per controllare i messaggi SOAP, è possibile applicare attributi alle classi, ai valori restituiti, ai parametri e ai campi trovati in un file del servizio Web XML (.asmx). È possibile utilizzare entrambi gli attributi elencati in "Attributi per il controllo della serializzazione XML" e "Attributi per il controllo della serializzazione SOAP codificata", dal momento che un servizio Web XML può utilizzare sia lo stile SOAP letterale che quello codificato. Per altre informazioni sull'uso di attributi per controllare l'XML generato da un servizio Web XML, vedere [Serializzazione XML con servizi Web XML](xml-serialization-with-xml-web-services.md). Per ulteriori informazioni sui servizi Web SOAP e XML, vedere [Personalizzazione della formattazione dei messaggi SOAP](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dkwy2d72(v=vs.100)).

## <a name="security-considerations-for-xmlserializer-applications"></a>Considerazioni sulla sicurezza per le applicazioni XmlSerializer

Quando si crea un'applicazione che utilizza **XmlSerializer**, tenere presente i seguenti elementi e le relative implicazioni:

- La classe **XmlSerializer** crea file C# (CS) e li compila in file DLL nella directory denominata dalla variabile di ambiente TEMP. La serializzazione viene eseguita con questi file DLL.

  > [!NOTE]
  > Questi assembly di serializzazione possono essere generati in anticipo ed essere firmati tramite lo strumento SGen.exe. Tale funzione non è disponibile per i server di servizi Web. In altre parole, è disponibile solo per l'utilizzo client e per la serializzazione manuale.

  Il codice e le DLL sono vulnerabili a un processo dannoso al momento della creazione e della compilazione. Se si utilizza un computer su cui è in esecuzione Microsoft Windows NT 4.0 o versioni successive, è possibile che due o più utenti condividano la directory TEMP. La condivisione di una directory TEMP è pericolosa se i due account hanno privilegi di sicurezza diversi e se l'account con privilegi più elevati esegue un'applicazione con **XmlSerializer**. In tal caso, un utente può compromettere la sicurezza del computer sostituendo il file cs o dll compilato. Per ovviare a questo problema, accertarsi sempre che ciascun account del computer disponga del proprio profilo. Per impostazione predefinita, la variabile di ambiente TEMP fa riferimento a una directory diversa per ciascun account.

- Se un utente malintenzionato invia un flusso continuo di dati XML a un server Web (attacco Denial of Service), **XmlSerializer** continua a elaborare i dati fino all'esaurimento delle risorse del computer.

  Questo tipo di attacco può essere impedito se si utilizza un computer su cui è in esecuzione Internet Information Services (IIS) e l'applicazione è in esecuzione all'interno di IIS. IIS dispone di un modulo di verifica che non elabora i flussi maggiori di una determinata dimensione (l'impostazione predefinita è 4 KB). Se si crea un'applicazione che non usa IIS e che esegue la deserializzazione con **XmlSerializer**, è necessario implementare un controllo simile per impedire un attacco Denial of Service.

- **XmlSerializer** serializza i dati ed esegue tutto il codice usando qualsiasi tipo assegnato.

  Un oggetto non autorizzato può presentare una minaccia in due modi. L'oggetto può eseguire codice dannoso o inserire codice dannoso nel file C# creato da **XmlSerializer**. Nel primo caso, se un oggetto non autorizzato tenta di eseguire una procedura distruttiva, la sicurezza di accesso al codice consente di impedire eventuali danni. Nel secondo caso, esiste una possibilità teorica che un oggetto non autorizzato possa inserire in qualche modo codice nel file C# creato da **XmlSerializer**. Sebbene questo problema sia stato esaminato in modo approfondito e tale attacco è considerato improbabile, è necessario prendere la precauzione di non serializzare mai dati con un tipo ignoto e non attendibile.

- I dati sensibili serializzati potrebbero essere vulnerabili.

  Dopo che **XmlSerializer** ha serializzato i dati, è possibile archiviarli come file XML o altro archivio dati. Se l'archivio dati è disponibile per altri processi o è visibile su una Intranet o Internet, i dati possono essere rubati e utilizzati in modo dannoso. Ad esempio, se si crea un'applicazione che serializza ordini che includono numeri di carta di credito, i dati risultano essere estremamente riservati. Per evitare ciò, proteggere sempre l'archivio per i dati ed eseguire le operazioni per mantenerli privati.

## <a name="serialization-of-a-simple-class"></a>Serializzazione di una classe semplice

Nell'esempio di codice riportato di seguito viene mostrata una classe di base con un campo pubblico.

```vb
Public Class OrderForm
    Public OrderDate As DateTime
End Class
```

```csharp
public class OrderForm
{
    public DateTime OrderDate;
}
```

Quando un'istanza di questa classe viene serializzata, potrebbe assomigliare agli elementi seguenti.

```xml
<OrderForm>
    <OrderDate>12/12/01</OrderDate>
</OrderForm>
```

Per altri esempi di serializzazione, vedere [Esempi di serializzazione XML](examples-of-xml-serialization.md).

## <a name="items-that-can-be-serialized"></a>Elementi che possono essere serializzati

Gli elementi seguenti possono essere serializzati con la classe **XmlSerializer**:

- Proprietà di lettura/scrittura pubbliche e campi di classi pubbliche.

- Classi che implementano **ICollection** o **IEnumerable**.

  > [!NOTE]
  > Vengono serializzate solo le raccolte e non le proprietà pubbliche.

- Oggetti **XmlElement**.

- Oggetti **XmlNode**.

- Oggetti **DataSet**.

 Per altre informazioni sulla serializzazione o la deserializzazione di oggetti, vedere [Procedura: Serializzare un oggetto](how-to-serialize-an-object.md) e [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md).

## <a name="advantages-of-using-xml-serialization"></a>Vantaggi dell'utilizzo della serializzazione XML

La classe **XmlSerializer** offre un controllo completo e flessibile quando si serializza un oggetto come XML. Se si sta creando un servizio Web XML, è possibile applicare attributi che controllano la serializzazione su classi e membri in modo da assicurare che l'output XML sia conforme a uno schema specifico.

Ad esempio, **XmlSerializer** permette di:

- Specificare se un campo o una proprietà devono essere codificati come attributo o elemento.

- Specificare un spazio dei nomi XML da utilizzare.

- Specificare il nome di un elemento o di un attributo se un nome di campo o proprietà non è appropriato.

Un altro vantaggio della serializzazione XML è che non si hanno vincoli sulle applicazioni in fase di sviluppo, finché il flusso XML generato sia conforme a uno schema specifico. Immaginare uno schema utilizzato per descrivere libri. Lo schema riporta un elemento titolo, autore, editore autore e numero ISBN. È possibile sviluppare un'applicazione che elabori i dati XML in qualsiasi modo desiderato, ad esempio, come un ordine di libri o come inventario di libri. In entrambi i casi, l'unico requisito è che il flusso XML sia conforme allo schema XSD (XML Schema definition) specificato.

## <a name="xml-serialization-considerations"></a>Considerazioni sulla serializzazione XML

Di seguito sono riportati alcuni aspetti da tenere presenti quando si usa la classe **XmlSerializer**:

- Lo strumento Sgen.exe è progettato espressamente per generare assembly di serializzazione per prestazioni ottimali.

- I dati serializzati contengono solo i dati stessi e la struttura delle classi. Le informazioni sull'identità e sull'assembly non sono incluse.

- È possibile serializzare solo le proprietà e i campi pubblici. Le proprietà devono disporre di funzioni di accesso pubbliche (metodi get e set). Se è necessario serializzare dati non pubblici, utilizzare la classe <xref:System.Runtime.Serialization.DataContractSerializer> anziché la serializzazione XML.

- Una classe deve disporre di un costruttore senza parametri per essere serializzata da **XmlSerializer**.

- I metodi non possono essere serializzati.

- **XmlSerializer** può elaborare le classi che implementano **IEnumerable** o **ICollection** in modo diverso se queste classi soddisfano determinati requisiti, indicati di seguito.

  Una classe che implementa **IEnumerable** deve implementare un metodo **Add** pubblico che accetta un solo parametro. Il parametro del metodo **Add** deve essere coerente (polimorfico) al tipo restituito dalla proprietà **IEnumerator.Current** restituita dal metodo **GetEnumerator**.

  Una classe che implementa **ICollection** oltre a **IEnumerable**, ad esempio **CollectionBase**, deve includere una proprietà indicizzata **Item** pubblica (indicizzatore in C#) che accetta un intero e una proprietà **Count** pubblica di tipo **integer**. Il parametro passato al metodo **Add** deve essere dello stesso tipo di quello restituito dalla proprietà **Item** o una delle basi di tale tipo.

  Per le classi che implementano **ICollection**, i valori da serializzare vengono recuperati dalla proprietà **Item** indicizzata anziché chiamando **GetEnumerator**. Inoltre, le proprietà e i campi pubblici non vengono serializzati, ad eccezione dei campi pubblici che restituiscono un'altra classe di raccolte (una che implementa **ICollection**). Per un esempio, vedere [Esempi di serializzazione XML](examples-of-xml-serialization.md).

## <a name="xsd-data-type-mapping"></a>Mappatura del tipo di dati XSD

Il documento W3C intitolato [XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/) specifica i tipi di dati semplici consentiti in uno schema XSD (XML Schema Definition Language). Per molti di questi, ad esempio **int** e **decimal**, esiste un tipo di dati corrispondente in .NET Framework. Tuttavia, per alcuni tipi di dati XML non esiste un tipo di dati corrispondente in .NET Framework, ad esempio il tipo di dati **NMTOKEN**. Se in questi casi si usa lo strumento XML Schema Definition ([strumento XML Schema Definition, Xsd.exe](xml-schema-definition-tool-xsd-exe.md)) per generare classi da uno schema, viene applicato un attributo appropriato a un membro di tipo stringa e la relativa proprietà **DataType** viene impostata sul nome del tipo di dati XML. Ad esempio, se uno schema contiene un elemento denominato "MyToken" con il tipo di dati XML **NMTOKEN**, la classe generata può contenere un membro come quello mostrato nell'esempio seguente.

```vb
<XmlElement(DataType:="NMTOKEN")> _
Public MyToken As String
```

```csharp
[XmlElement(DataType = "NMTOKEN")]
public string MyToken;
```

Analogamente, se si crea una classe che deve essere conforme a un oggetto XML Schema (XSD) specifico, è necessario applicare l'attributo appropriato e impostarne la proprietà **DataType** sul nome del tipo di dati XML desiderato.

Per un elenco completo dei mapping dei tipi, vedere la proprietà **DataType** per una delle classi di attributo seguenti:

- <xref:System.Xml.Serialization.SoapAttributeAttribute>

- <xref:System.Xml.Serialization.SoapElementAttribute>

- <xref:System.Xml.Serialization.XmlArrayItemAttribute>

- <xref:System.Xml.Serialization.XmlAttributeAttribute>

- <xref:System.Xml.Serialization.XmlElementAttribute>

- <xref:System.Xml.Serialization.XmlRootAttribute>

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.IO.FileStream>
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione](index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Esempi di serializzazione XML](examples-of-xml-serialization.md)
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
