---
title: Esempio di estensioni non fortemente tipizzate
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: 4d92f45382361c61fe9e7ac85ff5d604a2c87b27
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592206"
---
# <a name="loosely-typed-extensions-sample"></a><span data-ttu-id="4afde-102">Esempio di estensioni non fortemente tipizzate</span><span class="sxs-lookup"><span data-stu-id="4afde-102">Loosely-Typed Extensions Sample</span></span>
<span data-ttu-id="4afde-103">Il modello a oggetti di diffusione fornisce supporto dettagliato per lavorare con dati dell'estensione: informazioni presenti nella rappresentazione XML di un feed ma non esposte in modo esplicito da classi quali <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="4afde-103">The Syndication object model provides rich support for working with extension data—information that is present in a syndication feed's XML representation but not explicitly exposed by classes such as <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="4afde-104">Questo esempio illustra le tecniche di base per lavorare con i dati dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="4afde-104">This sample illustrates the basic techniques for working with extension data.</span></span>  
  
 <span data-ttu-id="4afde-105">Nell'esempio seguente viene utilizzata la classe <xref:System.ServiceModel.Syndication.SyndicationFeed> a scopo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="4afde-105">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="4afde-106">Tuttavia, i modelli illustrati in questo esempio possono essere usati con tutte le classi di diffusione che supportano dati di estensione:</span><span class="sxs-lookup"><span data-stu-id="4afde-106">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data:</span></span>  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a><span data-ttu-id="4afde-107">Esempio XML</span><span class="sxs-lookup"><span data-stu-id="4afde-107">Sample XML</span></span>  
 <span data-ttu-id="4afde-108">A scopo di riferimento, in questo esempio viene utilizzato il documento XML seguente.</span><span class="sxs-lookup"><span data-stu-id="4afde-108">For reference, the following XML document is used in this sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
```  
  
 <span data-ttu-id="4afde-109">Questo documento contiene le seguenti porzioni di dati dell'estensione:</span><span class="sxs-lookup"><span data-stu-id="4afde-109">This document contains the following pieces of extension data:</span></span>  
  
- <span data-ttu-id="4afde-110">Attributo `myAttribute` dell'elemento `<feed>`.</span><span class="sxs-lookup"><span data-stu-id="4afde-110">The `myAttribute` attribute of the `<feed>` element.</span></span>  
  
- <span data-ttu-id="4afde-111">`<simpleString>` elemento.</span><span class="sxs-lookup"><span data-stu-id="4afde-111">`<simpleString>` element.</span></span>  
  
- <span data-ttu-id="4afde-112">`<DataContractExtension>` elemento.</span><span class="sxs-lookup"><span data-stu-id="4afde-112">`<DataContractExtension>` element.</span></span>  
  
- <span data-ttu-id="4afde-113">`<XmlSerializerExtension>` elemento.</span><span class="sxs-lookup"><span data-stu-id="4afde-113">`<XmlSerializerExtension>` element.</span></span>  
  
- <span data-ttu-id="4afde-114">`<xElementExtension>` elemento.</span><span class="sxs-lookup"><span data-stu-id="4afde-114">`<xElementExtension>` element.</span></span>  
  
## <a name="writing-extension-data"></a><span data-ttu-id="4afde-115">Scrittura dati dell'estensione</span><span class="sxs-lookup"><span data-stu-id="4afde-115">Writing Extension Data</span></span>  
 <span data-ttu-id="4afde-116">Le estensioni dell'attributo vengono create aggiungendo voci alla raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4afde-116">Attribute extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection as shown in the following sample code.</span></span>  
  
```  
//Attribute extensions are stored in a dictionary indexed by   
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 <span data-ttu-id="4afde-117">Le estensioni dell'elemento vengono create aggiungendo voci alla raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="4afde-117">Element extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection.</span></span> <span data-ttu-id="4afde-118">Queste estensioni possono essere valori di base quali stringhe, serializzazioni XML di oggetti .NET Framework o nodi XML codificati a mano.</span><span class="sxs-lookup"><span data-stu-id="4afde-118">These extensions can by basic values such as strings, XML serializations of .NET Framework objects, or XML nodes coded by hand.</span></span>  
  
 <span data-ttu-id="4afde-119">Il codice di esempio seguente crea un elemento dell'estensione denominato `simpleString`.</span><span class="sxs-lookup"><span data-stu-id="4afde-119">The following sample code creates an extension element named `simpleString`.</span></span>  
  
```  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 <span data-ttu-id="4afde-120">Lo spazio dei nomi XML per questo elemento è lo spazio dei nomi vuoto ("") e il valore è un nodo di testo che contiene la stringa "hello, world!".</span><span class="sxs-lookup"><span data-stu-id="4afde-120">The XML namespace for this element is the empty namespace ("") and its value is a text node that contains the string "hello, world!".</span></span>  
  
 <span data-ttu-id="4afde-121">Un modo per creare estensioni dell'elemento complesse costituite da molti elementi annidati, consiste nell'utilizzare le API .NET Framework per la serializzazione (sia <xref:System.Runtime.Serialization.DataContractSerializer> sia <xref:System.Xml.Serialization.XmlSerializer> sono supportate), come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="4afde-121">One way to create complex element extensions that consist of many nested elements is to use the .NET Framework APIs for serialization (both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported) as shown in the following examples.</span></span>  
  
```  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 <span data-ttu-id="4afde-122">In questo esempio, `DataContractExtension` e `XmlSerializerExtension` sono tipi personalizzati scritti per l'utilizzo con un serializzatore.</span><span class="sxs-lookup"><span data-stu-id="4afde-122">In this example, the `DataContractExtension` and `XmlSerializerExtension` are custom types written for use with a serializer.</span></span>  
  
 <span data-ttu-id="4afde-123">La classe <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> può essere utilizzata anche per creare estensioni dell'elemento da un'istanza <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="4afde-123">The <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> class can also be used to create element extensions from an <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="4afde-124">Ciò consente una facile integrazione con l'elaborazione API XML ad esempio <xref:System.Xml.Linq.XElement> come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4afde-124">This allows for easy integration with XML processing APIs such as <xref:System.Xml.Linq.XElement> as shown in the following sample code.</span></span>  
  
```  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),   
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a><span data-ttu-id="4afde-125">Lettura dati dell'estensione</span><span class="sxs-lookup"><span data-stu-id="4afde-125">Reading Extension Data</span></span>  
 <span data-ttu-id="4afde-126">I valori per le estensioni dell'attributo possono essere ottenuti cercando l'attributo nella raccolta <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> tramite la classe <xref:System.Xml.XmlQualifiedName> come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4afde-126">The values for attribute extensions can be obtained by looking up the attribute in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection by its <xref:System.Xml.XmlQualifiedName> as shown in the following sample code.</span></span>  
  
```  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 <span data-ttu-id="4afde-127">L'accesso alle estensioni dell'elemento viene effettuato utilizzando il metodo `ReadElementExtensions<T>`.</span><span class="sxs-lookup"><span data-stu-id="4afde-127">Element extensions are accessed using the `ReadElementExtensions<T>` method.</span></span>  
  
```  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
```  
  
 <span data-ttu-id="4afde-128">È anche possibile ottenere un `XmlReader` per estensioni dell'elemento singole utilizzando il metodo <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>.</span><span class="sxs-lookup"><span data-stu-id="4afde-128">It is also possible to obtain an `XmlReader` at individual element extensions by using the <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> method.</span></span>  
  
```  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4afde-129">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="4afde-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4afde-130">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4afde-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4afde-131">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4afde-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="4afde-132">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4afde-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4afde-133">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="4afde-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4afde-134">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="4afde-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4afde-135">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="4afde-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4afde-136">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="4afde-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="4afde-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afde-137">See also</span></span>

- [<span data-ttu-id="4afde-138">Estensioni fortemente tipizzate</span><span class="sxs-lookup"><span data-stu-id="4afde-138">Strongly-Typed Extensions</span></span>](../../../../docs/framework/wcf/samples/strongly-typed-extensions-sample.md)
- [<span data-ttu-id="4afde-139">Diffusione WCF</span><span class="sxs-lookup"><span data-stu-id="4afde-139">WCF Syndication</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
