---
title: Cenni preliminari sulla classe XDocument (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f51808a64d51fb354159df1a7323ad2fc26eedc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="b2d37-102">Cenni preliminari sulla classe XDocument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2d37-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="b2d37-103">In questo argomento introduce la <xref:System.Xml.Linq.XDocument>classe.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="b2d37-104">Cenni preliminari sulla classe XDocument</span><span class="sxs-lookup"><span data-stu-id="b2d37-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="b2d37-105">La <xref:System.Xml.Linq.XDocument>classe contiene le informazioni necessarie per un documento XML valido.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="b2d37-106">ovvero una dichiarazione XML, istruzioni di elaborazione e commenti.</span><span class="sxs-lookup"><span data-stu-id="b2d37-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="b2d37-107">Si noti che è necessario solo creare <xref:System.Xml.Linq.XDocument>oggetti se richiesta la funzionalità specifica fornita dalla <xref:System.Xml.Linq.XDocument>classe.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="b2d37-108">In molti casi, è possibile utilizzare direttamente con <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2d37-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="b2d37-109">Utilizzo diretto di <xref:System.Xml.Linq.XElement>è un modello di programmazione più semplice.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2d37-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="b2d37-110"><xref:System.Xml.Linq.XDocument>deriva da <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="b2d37-111">pertanto può contenere nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="b2d37-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="b2d37-112">Tuttavia, <xref:System.Xml.Linq.XDocument>gli oggetti possono avere un solo elemento figlio <xref:System.Xml.Linq.XElement>nodo.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="b2d37-113">in conformità allo standard XML, secondo il quale un documento XML può contenere un unico elemento radice.</span><span class="sxs-lookup"><span data-stu-id="b2d37-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="b2d37-114">Componenti di XDocument</span><span class="sxs-lookup"><span data-stu-id="b2d37-114">Components of XDocument</span></span>  
 <span data-ttu-id="b2d37-115">Un <xref:System.Xml.Linq.XDocument>può contenere i seguenti elementi:</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="b2d37-116">Un <xref:System.Xml.Linq.XDeclaration>oggetto.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="b2d37-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="b2d37-117"><xref:System.Xml.Linq.XDeclaration>Consente di specificare le parti pertinenti di una dichiarazione XML: la versione XML, la codifica del documento, e se il documento XML è autonomo.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="b2d37-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="b2d37-118">Un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2d37-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="b2d37-119">Si tratta del nodo radice del documento XML.</span><span class="sxs-lookup"><span data-stu-id="b2d37-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="b2d37-120">Un numero qualsiasi di <xref:System.Xml.Linq.XProcessingInstruction>oggetti.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="b2d37-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="b2d37-121">Un'istruzione di elaborazione comunica informazioni a un'applicazione che elabora l'XML.</span><span class="sxs-lookup"><span data-stu-id="b2d37-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="b2d37-122">Un numero qualsiasi di <xref:System.Xml.Linq.XComment>oggetti.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="b2d37-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="b2d37-123">I commenti saranno elementi di pari livello dell'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="b2d37-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="b2d37-124">Il <xref:System.Xml.Linq.XComment>oggetto non può essere il primo argomento nell'elenco perché non è valido per un documento XML per iniziare con un commento.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="b2d37-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="b2d37-125">Un <xref:System.Xml.Linq.XDocumentType>per DTD.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="b2d37-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="b2d37-126">Quando si serializza un <xref:System.Xml.Linq.XDocument>, anche se `XDocument.Declaration` è `null`, l'output includerà una dichiarazione XML se il writer `Writer.Settings.OmitXmlDeclaration` impostato su `false` (predefinito).</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="b2d37-127">Per impostazione predefinita, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] imposta la versione su "1.0" e la codifica su "utf-8".</span><span class="sxs-lookup"><span data-stu-id="b2d37-127">By default, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="b2d37-128">Uso di XElement senza XDocument</span><span class="sxs-lookup"><span data-stu-id="b2d37-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="b2d37-129">Come accennato in precedenza, il <xref:System.Xml.Linq.XElement>è la classe principale nel [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] interfaccia di programmazione.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2d37-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface.</span></span> <span data-ttu-id="b2d37-130">In molti casi l'applicazione non richiederà la creazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="b2d37-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="b2d37-131">Utilizzando la <xref:System.Xml.Linq.XElement>classe, creare una struttura ad albero XML, aggiungervi altri alberi XML, modificare la struttura ad albero XML e salvare tale</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2d37-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="b2d37-132">Uso di XDocument</span><span class="sxs-lookup"><span data-stu-id="b2d37-132">Using XDocument</span></span>  
 <span data-ttu-id="b2d37-133">Per costruire un <xref:System.Xml.Linq.XDocument>, usare la costruzione funzionale, proprio come si trattasse di costruire <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="b2d37-134">Il codice seguente crea un <xref:System.Xml.Linq.XDocument>oggetto e relativi oggetti contenuti associati.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="b2d37-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="b2d37-135">Quando si esamina il file test.xml, si ottiene l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b2d37-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b2d37-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2d37-136">See Also</span></span>  
 [<span data-ttu-id="b2d37-137">LINQ to Cenni preliminari sulla programmazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2d37-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
