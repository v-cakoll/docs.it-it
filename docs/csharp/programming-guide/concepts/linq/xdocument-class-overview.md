---
title: Panoramica della classe XDocument (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 0d182593cfedd30042c4e3a5d776bb00ce267ff7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504858"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="a36ba-102">Panoramica della classe XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="a36ba-102">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="a36ba-103">In questo argomento viene descritta la classe <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="a36ba-104">Cenni preliminari sulla classe XDocument</span><span class="sxs-lookup"><span data-stu-id="a36ba-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="a36ba-105">La classe <xref:System.Xml.Linq.XDocument> include le informazioni necessarie per un documento XML valido,</span><span class="sxs-lookup"><span data-stu-id="a36ba-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="a36ba-106">ovvero una dichiarazione XML, istruzioni di elaborazione e commenti.</span><span class="sxs-lookup"><span data-stu-id="a36ba-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="a36ba-107">Notare che è necessario creare oggetti <xref:System.Xml.Linq.XDocument> solo se è richiesta la funzionalità specifica fornita dalla classe <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="a36ba-108">In molte circostanze è possibile usare direttamente <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a36ba-109">L'utilizzo diretto di <xref:System.Xml.Linq.XElement> corrisponde a un modello di programmazione più semplice.</span><span class="sxs-lookup"><span data-stu-id="a36ba-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="a36ba-110"><xref:System.Xml.Linq.XDocument> deriva da <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="a36ba-111">pertanto può contenere nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="a36ba-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="a36ba-112">Gli oggetti <xref:System.Xml.Linq.XDocument> possono contenere un solo nodo <xref:System.Xml.Linq.XElement> figlio,</span><span class="sxs-lookup"><span data-stu-id="a36ba-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="a36ba-113">in conformità allo standard XML, secondo il quale un documento XML può contenere un unico elemento radice.</span><span class="sxs-lookup"><span data-stu-id="a36ba-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="a36ba-114">Componenti di XDocument</span><span class="sxs-lookup"><span data-stu-id="a36ba-114">Components of XDocument</span></span>  
 <span data-ttu-id="a36ba-115">Un oggetto <xref:System.Xml.Linq.XDocument> può contenere i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a36ba-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="a36ba-116">Un unico oggetto <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="a36ba-117"><xref:System.Xml.Linq.XDeclaration> consente di specificare le parti pertinenti di una dichiarazione XML, ovvero la versione del codice XML, la codifica del documento e se il documento XML è autonomo.</span><span class="sxs-lookup"><span data-stu-id="a36ba-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="a36ba-118">Un unico oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="a36ba-119">Si tratta del nodo radice del documento XML.</span><span class="sxs-lookup"><span data-stu-id="a36ba-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="a36ba-120">Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="a36ba-121">Un'istruzione di elaborazione comunica informazioni a un'applicazione che elabora l'XML.</span><span class="sxs-lookup"><span data-stu-id="a36ba-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="a36ba-122">Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="a36ba-123">I commenti saranno elementi di pari livello dell'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="a36ba-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="a36ba-124">L'oggetto <xref:System.Xml.Linq.XComment> non può essere il primo argomento dell'elenco perché un documento XML non può iniziare con un commento.</span><span class="sxs-lookup"><span data-stu-id="a36ba-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="a36ba-125">Un unico oggetto <xref:System.Xml.Linq.XDocumentType> per DTD.</span><span class="sxs-lookup"><span data-stu-id="a36ba-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="a36ba-126">Quando si serializza un oggetto <xref:System.Xml.Linq.XDocument>, anche se `XDocument.Declaration` è `null`, l'output includerà una dichiarazione XML se per il writer `Writer.Settings.OmitXmlDeclaration` è impostato su `false` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="a36ba-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="a36ba-127">Per impostazione predefinita, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] imposta la versione su "1.0" e la codifica su "utf-8".</span><span class="sxs-lookup"><span data-stu-id="a36ba-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="a36ba-128">Uso di XElement senza XDocument</span><span class="sxs-lookup"><span data-stu-id="a36ba-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="a36ba-129">Come menzionato in precedenza, la classe <xref:System.Xml.Linq.XElement> è la classe principale dell'interfaccia di programmazione di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a36ba-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="a36ba-130">In molti casi l'applicazione non richiederà la creazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="a36ba-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="a36ba-131">Se si usa la classe <xref:System.Xml.Linq.XElement>, è possibile creare un albero XML, aggiungervi altri alberi XML, modificare l'albero XML e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="a36ba-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="a36ba-132">Uso di XDocument</span><span class="sxs-lookup"><span data-stu-id="a36ba-132">Using XDocument</span></span>  
 <span data-ttu-id="a36ba-133">Per costruire un oggetto <xref:System.Xml.Linq.XDocument>, usare la costruzione funzionale come se si trattasse di costruire oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a36ba-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="a36ba-134">Nel codice seguente vengono creati un oggetto <xref:System.Xml.Linq.XDocument> e i relativi oggetti contenuti associati.</span><span class="sxs-lookup"><span data-stu-id="a36ba-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="a36ba-135">Quando si esamina il file test.xml, si ottiene l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="a36ba-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="a36ba-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a36ba-136">See Also</span></span>

- [<span data-ttu-id="a36ba-137">Panoramica della programmazione con LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="a36ba-137">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
