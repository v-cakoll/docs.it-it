---
title: Esempio di estensioni fortemente tipizzate
ms.date: 03/30/2017
ms.assetid: 02220f11-1a83-441c-9e5a-85f9a9367572
ms.openlocfilehash: 3cfbcddfdc7700618d499dd41d3a8c3b629bf550
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183307"
---
# <a name="strongly-typed-extensions-sample"></a>Esempio di estensioni fortemente tipizzate
Nell'esempio seguente viene utilizzata la classe <xref:System.ServiceModel.Syndication.SyndicationFeed> a scopo esemplificativo. Tuttavia, i modelli illustrati in questo esempio possono essere usati con tutte le classi di diffusione che supportano dati di estensione.  
  
 Il modello a oggetti di diffusione (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> e classi correlate) supporta l'accesso non fortemente tipizzato ai dati dell'estensione utilizzando le proprietà <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>. Questo esempio illustra come fornire l'accesso fortemente tipizzato ai dati di estensione implementando classi derivate personalizzate di <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> che rendono disponibili alcune estensioni specifiche dell'applicazione come proprietà fortemente tipizzate.  
  
 Per esempio, viene illustrato come implementare un elemento dell'estensione definito nell'Atom Threading Extensions RFC proposto. Ciò ha mero scopo esemplificativo e questo esempio non va inteso come un'implementazione completa della specifica proposta.  
  
## <a name="sample-xml"></a>Esempio XML  
 Nell'esempio XML seguente viene illustrata una voce Atom 1.0 con un elemento dell'estensione `<in-reply-to>` aggiuntivo.  
  
```xml  
<entry>  
    <id>tag:example.org,2005:1,2</id>  
    <title type="text">Another response to the original</title>  
    <summary type="text">  
         This is a response to the original entry</summary>  
    <updated>2006-03-01T12:12:13Z</updated>  
    <link href="http://www.example.org/entries/1/2" />  
    <in-reply-to p3:ref="tag:example.org,2005:1"
                 p3:href="http://www.example.org/entries/1"
                 p3:type="application/xhtml+xml"
                 xmlns:p3="http://contoso.org/syndication/thread/1.0"
                 xmlns="http://contoso.org/syndication/thread/1.0">  
      <anotherElement xmlns="http://www.w3.org/2005/Atom">  
                     Some more data</anotherElement>  
      <aDifferentElement xmlns="http://www.w3.org/2005/Atom">  
                     Even more data</aDifferentElement>  
    </in-reply-to>  
</entry>  
```  
  
 L'elemento `<in-reply-to>` specifica tre`ref`attributi `type` `href`obbligatori ( , e ), consentendo al contempo la presenza di attributi di estensione ed elementi di estensione aggiuntivi.  
  
## <a name="modeling-the-in-reply-to-element"></a>Creazione dell'elemento "in risposta a"  
 In questo esempio, l'elemento `<in-reply-to>` viene modellato come CLR che implementa <xref:System.Xml.Serialization.IXmlSerializable>, che ne abilita l'utilizzo con <xref:System.Runtime.Serialization.DataContractSerializer>. Implementa anche alcuni metodi e proprietà per l'accesso ai dati dell'elemento, come mostra il codice di esempio seguente.  
  
```csharp  
[XmlRoot(ElementName = "in-reply-to", Namespace = "http://contoso.org/syndication/thread/1.0")]  
public class InReplyToElement : IXmlSerializable  
{  
    internal const string ElementName = "in-reply-to";  
    internal const string NsUri =
                  "http://contoso.org/syndication/thread/1.0";  
    private Dictionary<XmlQualifiedName, string> extensionAttributes;  
    private Collection<XElement> extensionElements;  
  
    public InReplyToElement()  
    {  
        this.extensionElements = new Collection<XElement>();  
        this.extensionAttributes = new Dictionary<XmlQualifiedName,
                                                          string>();  
    }  
  
    public Dictionary<XmlQualifiedName, string> AttributeExtensions  
    {  
        get { return this.extensionAttributes; }  
    }  
  
    public Collection<XElement> ElementExtensions  
    {  
        get { return this.extensionElements; }  
    }  
  
    public Uri Href  
    { get; set; }  
  
    public string MediaType  
    { get; set; }  
  
    public string Ref  
    { get; set; }  
  
    public Uri Source  
    { get; set; }  
}  
```  
  
 La classe `InReplyToElement` implementa proprietà per l'attributo obbligatorio (`HRef`, `MediaType` e `Source`), oltre a raccolte per utilizzare <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.  
  
 La classe `InReplyToElement` implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> che consente il controllo diretto su come le istanze dell'oggetto sono lette e scritte in XML. Il metodo `ReadXml` legge per primi i valori delle proprietà `Ref`, `HRef`, `Source` e `MediaType` dalla classe <xref:System.Xml.XmlReader> passata a esso. Qualsiasi attributo sconosciuto viene archiviato nella raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>. Quando tutti gli attributi sono stati letti, il metodo <xref:System.Xml.XmlReader.ReadStartElement> viene chiamato per far avanzare il lettore all'elemento successivo. Poiché l'elemento modellato da questa classe non ha figli obbligatori, gli elementi figlio vengono memorizzati nel buffer nelle istanze `XElement` e archiviati nella raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, come illustrato nel codice seguente.  
  
```csharp
public void ReadXml(System.Xml.XmlReader reader)  
{  
    bool isEmpty = reader.IsEmptyElement;  
  
    if (reader.HasAttributes)  
    {  
        for (int i = 0; i < reader.AttributeCount; i++)  
        {  
            reader.MoveToNextAttribute();  
  
            if (reader.NamespaceURI == "")  
            {  
                if (reader.LocalName == "ref")  
                {  
                    this.Ref = reader.Value;  
                }  
                else if (reader.LocalName == "href")  
                {  
                    this.Href = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "source")  
                {  
                    this.Source = new Uri(reader.Value);  
                }  
                else if (reader.LocalName == "type")  
                {  
                    this.MediaType = reader.Value;  
                }  
                else  
                {  
                    this.AttributeExtensions.Add(new
                                 XmlQualifiedName(reader.LocalName,
                                 reader.NamespaceURI),
                                 reader.Value);  
                }  
            }  
        }  
    }  
  
    reader.ReadStartElement();  
  
    if (!isEmpty)  
    {  
        while (reader.IsStartElement())  
        {  
            ElementExtensions.Add(  
                  (XElement) XElement.ReadFrom(reader));  
        }  
        reader.ReadEndElement();  
    }  
}  
```  
  
 In `WriteXml`, il metodo `InReplyToElement` scrive per primi i valori delle proprietà `Ref`, `HRef`, `Source``MediaType` come attributi XML (`WriteXml` non è responsabile per la scrittura dell'elemento esterno effettivo, come quello effettuato dal chiamante di `WriteXml`). Scrive inoltre il contenuto di <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> nel writer, come illustrato nel codice seguente.  
  
```csharp
public void WriteXml(System.Xml.XmlWriter writer)  
{  
    if (this.Ref != null)  
    {  
        writer.WriteAttributeString("ref", InReplyToElement.NsUri,
                                            this.Ref);  
    }  
    if (this.Href != null)  
    {  
        writer.WriteAttributeString("href", InReplyToElement.NsUri,
                                                this.Href.ToString());  
    }  
    if (this.Source != null)  
    {  
        writer.WriteAttributeString("source", InReplyToElement.NsUri,
                                              this.Source.ToString());  
    }  
    if (this.MediaType != null)  
    {  
        writer.WriteAttributeString("type", InReplyToElement.NsUri,
                                                    this.MediaType);  
    }  
  
    foreach (KeyValuePair<XmlQualifiedName, string> kvp in
                                             this.AttributeExtensions)  
    {  
        writer.WriteAttributeString(kvp.Key.Name, kvp.Key.Namespace,
                                                   kvp.Value);  
    }  
  
    foreach (XElement element in this.ElementExtensions)  
    {  
        element.WriteTo(writer);  
    }  
}  
```  
  
## <a name="threadedfeed-and-threadeditem"></a>ThreadedFeed e ThreadedItem  
 Nell'esempio, `SyndicationItems` con le estensioni `InReplyTo` essi sono modellati dalla classe `ThreadedItem`. Similmente, la classe `ThreadedFeed` è un `SyndicationFeed` i cui elementi sono tutti istanze di `ThreadedItem`.  
  
 La classe `ThreadedFeed` eredita da `SyndicationFeed` ed esegue l'override di `OnCreateItem` per restituire `ThreadedItem`. Implementa inoltre un metodo per l'accesso alla raccolta `Items` come `ThreadedItems`, come illustrato nel codice seguente.  
  
```csharp
public class ThreadedFeed : SyndicationFeed  
{  
    public ThreadedFeed()  
    {  
    }  
  
    public IEnumerable<ThreadedItem> ThreadedItems  
    {  
        get  
        {  
            return this.Items.Cast<ThreadedItem>();  
        }  
    }  
  
    protected override SyndicationItem CreateItem()  
    {  
        return new ThreadedItem();  
    }  
}  
```  
  
 La classe `ThreadedItem` eredita da `SyndicationItem` e rende `InReplyToElement` una proprietà fortemente tipizzata. Ciò fornisce accesso conveniente a livello di codice alle estensioni dati `InReplyTo`. Implementa inoltre `TryParseElement` e `WriteElementExtensions` per la lettura e la scrittura dei dati di estensione corrispondenti, come illustrato nel codice seguente.  
  
```csharp
public class ThreadedItem : SyndicationItem  
{  
    private InReplyToElement inReplyTo;  
    // Constructors  
        public ThreadedItem()  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
        public ThreadedItem(string title, string content, Uri itemAlternateLink, string id, DateTimeOffset lastUpdatedTime) : base(title, content, itemAlternateLink, id, lastUpdatedTime)  
        {  
            inReplyTo = new InReplyToElement();  
        }  
  
    public InReplyToElement InReplyTo  
    {  
        get { return this.inReplyTo; }  
    }  
  
    protected override bool TryParseElement(  
                        System.Xml.XmlReader reader,
                        string version)  
    {  
        if (version == SyndicationVersions.Atom10 &&  
            reader.NamespaceURI == InReplyToElement.NsUri &&  
            reader.LocalName == InReplyToElement.ElementName)  
        {  
            this.inReplyTo = new InReplyToElement();  
  
            this.InReplyTo.ReadXml(reader);  
  
            return true;  
        }  
        else  
        {  
            return base.TryParseElement(reader, version);  
        }  
    }  
  
    protected override void WriteElementExtensions(XmlWriter writer,
                                                 string version)  
    {  
        if (this.InReplyTo != null &&
                     version == SyndicationVersions.Atom10)  
        {  
            writer.WriteStartElement(InReplyToElement.ElementName,
                                           InReplyToElement.NsUri);  
            this.InReplyTo.WriteXml(writer);  
            writer.WriteEndElement();  
        }  
  
        base.WriteElementExtensions(writer, version);  
    }  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
