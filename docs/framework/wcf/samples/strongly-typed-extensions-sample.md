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
# <a name="strongly-typed-extensions-sample"></a><span data-ttu-id="94de8-102">Esempio di estensioni fortemente tipizzate</span><span class="sxs-lookup"><span data-stu-id="94de8-102">Strongly-Typed Extensions Sample</span></span>
<span data-ttu-id="94de8-103">Nell'esempio seguente viene utilizzata la classe <xref:System.ServiceModel.Syndication.SyndicationFeed> a scopo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="94de8-103">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="94de8-104">Tuttavia, i modelli illustrati in questo esempio possono essere usati con tutte le classi di diffusione che supportano dati di estensione.</span><span class="sxs-lookup"><span data-stu-id="94de8-104">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data.</span></span>  
  
 <span data-ttu-id="94de8-105">Il modello a oggetti di diffusione (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem> e classi correlate) supporta l'accesso non fortemente tipizzato ai dati dell'estensione utilizzando le proprietà <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="94de8-105">The Syndication object model (<xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, and related classes) supports loosely-typed access to extension data by using the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> properties.</span></span> <span data-ttu-id="94de8-106">Questo esempio illustra come fornire l'accesso fortemente tipizzato ai dati di estensione implementando classi derivate personalizzate di <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> che rendono disponibili alcune estensioni specifiche dell'applicazione come proprietà fortemente tipizzate.</span><span class="sxs-lookup"><span data-stu-id="94de8-106">This sample shows how to provide strongly-typed access to extension data by implementing custom derived classes of <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> that make available certain application-specific extensions as strongly-typed properties.</span></span>  
  
 <span data-ttu-id="94de8-107">Per esempio, viene illustrato come implementare un elemento dell'estensione definito nell'Atom Threading Extensions RFC proposto.</span><span class="sxs-lookup"><span data-stu-id="94de8-107">As an example, this sample shows how to implement an extension element defined in the proposed Atom Threading Extensions RFC.</span></span> <span data-ttu-id="94de8-108">Ciò ha mero scopo esemplificativo e questo esempio non va inteso come un'implementazione completa della specifica proposta.</span><span class="sxs-lookup"><span data-stu-id="94de8-108">This is for demonstration purposes only and this sample is not intended to be a full implementation of the proposed specification.</span></span>  
  
## <a name="sample-xml"></a><span data-ttu-id="94de8-109">Esempio XML</span><span class="sxs-lookup"><span data-stu-id="94de8-109">Sample XML</span></span>  
 <span data-ttu-id="94de8-110">Nell'esempio XML seguente viene illustrata una voce Atom 1.0 con un elemento dell'estensione `<in-reply-to>` aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="94de8-110">The following XML example shows an Atom 1.0 entry with an additional `<in-reply-to>` extension element.</span></span>  
  
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
  
 <span data-ttu-id="94de8-111">L'elemento `<in-reply-to>` specifica tre`ref`attributi `type` `href`obbligatori ( , e ), consentendo al contempo la presenza di attributi di estensione ed elementi di estensione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="94de8-111">The `<in-reply-to>` element specifies three required attributes (`ref`, `type` and `href`) while also allowing for the presence of additional extension attributes and extension elements.</span></span>  
  
## <a name="modeling-the-in-reply-to-element"></a><span data-ttu-id="94de8-112">Creazione dell'elemento "in risposta a"</span><span class="sxs-lookup"><span data-stu-id="94de8-112">Modeling the In-Reply-To element</span></span>  
 <span data-ttu-id="94de8-113">In questo esempio, l'elemento `<in-reply-to>` viene modellato come CLR che implementa <xref:System.Xml.Serialization.IXmlSerializable>, che ne abilita l'utilizzo con <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="94de8-113">In this sample, the `<in-reply-to>` element is modeled as CLR that implements <xref:System.Xml.Serialization.IXmlSerializable>, which enables its use with the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="94de8-114">Implementa anche alcuni metodi e proprietà per l'accesso ai dati dell'elemento, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-114">It also implements some methods and properties for accessing the element’s data, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="94de8-115">La classe `InReplyToElement` implementa proprietà per l'attributo obbligatorio (`HRef`, `MediaType` e `Source`), oltre a raccolte per utilizzare <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="94de8-115">The `InReplyToElement` class implements properties for the required attribute (`HRef`, `MediaType`, and `Source`) as well as collections to hold <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span></span>  
  
 <span data-ttu-id="94de8-116">La classe `InReplyToElement` implementa l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> che consente il controllo diretto su come le istanze dell'oggetto sono lette e scritte in XML.</span><span class="sxs-lookup"><span data-stu-id="94de8-116">The `InReplyToElement` class implements the <xref:System.Xml.Serialization.IXmlSerializable> interface, which allows direct control over how object instances are read from and written to XML.</span></span> <span data-ttu-id="94de8-117">Il metodo `ReadXml` legge per primi i valori delle proprietà `Ref`, `HRef`, `Source` e `MediaType` dalla classe <xref:System.Xml.XmlReader> passata a esso.</span><span class="sxs-lookup"><span data-stu-id="94de8-117">The `ReadXml` method first reads the values for the `Ref`, `HRef`, `Source`, and `MediaType` properties from the <xref:System.Xml.XmlReader> passed to it.</span></span> <span data-ttu-id="94de8-118">Qualsiasi attributo sconosciuto viene archiviato nella raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="94de8-118">Any unknown attributes are stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection.</span></span> <span data-ttu-id="94de8-119">Quando tutti gli attributi sono stati letti, il metodo <xref:System.Xml.XmlReader.ReadStartElement> viene chiamato per far avanzare il lettore all'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="94de8-119">When all the attributes have been read, <xref:System.Xml.XmlReader.ReadStartElement> is called to advance the reader to the next element.</span></span> <span data-ttu-id="94de8-120">Poiché l'elemento modellato da questa classe non ha figli obbligatori, gli elementi figlio vengono memorizzati nel buffer nelle istanze `XElement` e archiviati nella raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-120">Because the element modeled by this class has no required children, the child elements get buffered into `XElement` instances and stored in the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="94de8-121">In `WriteXml`, il metodo `InReplyToElement` scrive per primi i valori delle proprietà `Ref`, `HRef`, `Source``MediaType` come attributi XML (`WriteXml` non è responsabile per la scrittura dell'elemento esterno effettivo, come quello effettuato dal chiamante di `WriteXml`).</span><span class="sxs-lookup"><span data-stu-id="94de8-121">In `WriteXml`, the `InReplyToElement` method first writes out the values of the `Ref`, `HRef`, `Source`, and `MediaType` properties as XML attributes (`WriteXml` is not responsible for writing the actual outer element itself, as that done by the caller of `WriteXml`).</span></span> <span data-ttu-id="94de8-122">Scrive inoltre il contenuto di <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> e <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> nel writer, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-122">It also writes the contents of the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> and <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> to the writer, as shown in the following code.</span></span>  
  
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
  
## <a name="threadedfeed-and-threadeditem"></a><span data-ttu-id="94de8-123">ThreadedFeed e ThreadedItem</span><span class="sxs-lookup"><span data-stu-id="94de8-123">ThreadedFeed and ThreadedItem</span></span>  
 <span data-ttu-id="94de8-124">Nell'esempio, `SyndicationItems` con le estensioni `InReplyTo` essi sono modellati dalla classe `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="94de8-124">In the sample, `SyndicationItems` with `InReplyTo` extensions are modeled by the `ThreadedItem` class.</span></span> <span data-ttu-id="94de8-125">Similmente, la classe `ThreadedFeed` è un `SyndicationFeed` i cui elementi sono tutti istanze di `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="94de8-125">Similarly, the `ThreadedFeed` class is a `SyndicationFeed` whose items are all instances of `ThreadedItem`.</span></span>  
  
 <span data-ttu-id="94de8-126">La classe `ThreadedFeed` eredita da `SyndicationFeed` ed esegue l'override di `OnCreateItem` per restituire `ThreadedItem`.</span><span class="sxs-lookup"><span data-stu-id="94de8-126">The `ThreadedFeed` class inherits from `SyndicationFeed` and overrides `OnCreateItem` to return a `ThreadedItem`.</span></span> <span data-ttu-id="94de8-127">Implementa inoltre un metodo per l'accesso alla raccolta `Items` come `ThreadedItems`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-127">It also implements a method for accessing the `Items` collection as `ThreadedItems`, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="94de8-128">La classe `ThreadedItem` eredita da `SyndicationItem` e rende `InReplyToElement` una proprietà fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="94de8-128">The class `ThreadedItem` inherits from `SyndicationItem` and makes `InReplyToElement` as a strongly-typed property.</span></span> <span data-ttu-id="94de8-129">Ciò fornisce accesso conveniente a livello di codice alle estensioni dati `InReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="94de8-129">This provides for convenient programmatic access to the `InReplyTo` extension data.</span></span> <span data-ttu-id="94de8-130">Implementa inoltre `TryParseElement` e `WriteElementExtensions` per la lettura e la scrittura dei dati di estensione corrispondenti, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-130">It also implements `TryParseElement` and `WriteElementExtensions` for reading and writing its extension data, as shown in the following code.</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="94de8-131">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="94de8-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="94de8-132">Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="94de8-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="94de8-133">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="94de8-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="94de8-134">Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="94de8-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="94de8-135">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="94de8-135">The samples may already be installed on your computer.</span></span> <span data-ttu-id="94de8-136">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="94de8-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="94de8-137">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="94de8-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="94de8-138">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="94de8-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StronglyTypedExtensions`  
