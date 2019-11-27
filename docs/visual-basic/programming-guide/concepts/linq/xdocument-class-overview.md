---
title: Panoramica della classe XDocument
ms.date: 07/20/2015
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
ms.openlocfilehash: cbc1ccca53978da07f31c0ba7e54eca9f06b0e72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349295"
---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="9c988-102">Cenni preliminari sulla classe XDocument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c988-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="9c988-103">In questo argomento viene descritta la classe <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="9c988-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="9c988-104">Cenni preliminari sulla classe XDocument</span><span class="sxs-lookup"><span data-stu-id="9c988-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="9c988-105">La classe <xref:System.Xml.Linq.XDocument> include le informazioni necessarie per un documento XML valido,</span><span class="sxs-lookup"><span data-stu-id="9c988-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="9c988-106">ovvero una dichiarazione XML, istruzioni di elaborazione e commenti.</span><span class="sxs-lookup"><span data-stu-id="9c988-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="9c988-107">Notare che è necessario creare oggetti <xref:System.Xml.Linq.XDocument> solo se è richiesta la funzionalità specifica fornita dalla classe <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="9c988-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="9c988-108">In molte circostanze è possibile usare direttamente <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9c988-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="9c988-109">L'utilizzo diretto di <xref:System.Xml.Linq.XElement> corrisponde a un modello di programmazione più semplice.</span><span class="sxs-lookup"><span data-stu-id="9c988-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="9c988-110"><xref:System.Xml.Linq.XDocument> deriva da <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="9c988-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="9c988-111">pertanto può contenere nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="9c988-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="9c988-112">Gli oggetti <xref:System.Xml.Linq.XDocument> possono contenere un solo nodo <xref:System.Xml.Linq.XElement> figlio,</span><span class="sxs-lookup"><span data-stu-id="9c988-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="9c988-113">in conformità allo standard XML, secondo il quale un documento XML può contenere un unico elemento radice.</span><span class="sxs-lookup"><span data-stu-id="9c988-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="9c988-114">Componenti di XDocument</span><span class="sxs-lookup"><span data-stu-id="9c988-114">Components of XDocument</span></span>  
 <span data-ttu-id="9c988-115">Un oggetto <xref:System.Xml.Linq.XDocument> può contenere i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9c988-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="9c988-116">Un unico oggetto <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="9c988-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="9c988-117"><xref:System.Xml.Linq.XDeclaration> consente di specificare le parti pertinenti di una dichiarazione XML, ovvero la versione del codice XML, la codifica del documento e se il documento XML è autonomo.</span><span class="sxs-lookup"><span data-stu-id="9c988-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="9c988-118">Un unico oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9c988-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="9c988-119">Si tratta del nodo radice del documento XML.</span><span class="sxs-lookup"><span data-stu-id="9c988-119">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="9c988-120">Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="9c988-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="9c988-121">Un'istruzione di elaborazione comunica informazioni a un'applicazione che elabora l'XML.</span><span class="sxs-lookup"><span data-stu-id="9c988-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="9c988-122">Un qualsiasi numero di oggetti <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="9c988-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="9c988-123">I commenti saranno elementi di pari livello dell'elemento radice.</span><span class="sxs-lookup"><span data-stu-id="9c988-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="9c988-124">L'oggetto <xref:System.Xml.Linq.XComment> non può essere il primo argomento dell'elenco perché un documento XML non può iniziare con un commento.</span><span class="sxs-lookup"><span data-stu-id="9c988-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="9c988-125">Un unico oggetto <xref:System.Xml.Linq.XDocumentType> per DTD.</span><span class="sxs-lookup"><span data-stu-id="9c988-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="9c988-126">Quando si serializza un oggetto <xref:System.Xml.Linq.XDocument>, anche se `XDocument.Declaration` è `null`, l'output includerà una dichiarazione XML se per il writer `Writer.Settings.OmitXmlDeclaration` è impostato su `false` (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="9c988-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="9c988-127">Per impostazione predefinita, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] imposta la versione su "1.0" e la codifica su "utf-8".</span><span class="sxs-lookup"><span data-stu-id="9c988-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="9c988-128">Uso di XElement senza XDocument</span><span class="sxs-lookup"><span data-stu-id="9c988-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="9c988-129">Come menzionato in precedenza, la classe <xref:System.Xml.Linq.XElement> è la classe principale dell'interfaccia di programmazione di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c988-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="9c988-130">In molti casi l'applicazione non richiederà la creazione di un documento.</span><span class="sxs-lookup"><span data-stu-id="9c988-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="9c988-131">Se si usa la classe <xref:System.Xml.Linq.XElement>, è possibile creare un albero XML, aggiungervi altri alberi XML, modificare l'albero XML e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="9c988-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="9c988-132">Uso di XDocument</span><span class="sxs-lookup"><span data-stu-id="9c988-132">Using XDocument</span></span>  
 <span data-ttu-id="9c988-133">Per costruire un oggetto <xref:System.Xml.Linq.XDocument>, usare la costruzione funzionale come se si trattasse di costruire oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9c988-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="9c988-134">Nel codice seguente vengono creati un oggetto <xref:System.Xml.Linq.XDocument> e i relativi oggetti contenuti associati.</span><span class="sxs-lookup"><span data-stu-id="9c988-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
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
  
 <span data-ttu-id="9c988-135">Quando si esamina il file test.xml, si ottiene l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="9c988-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c988-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c988-136">See also</span></span>

- [<span data-ttu-id="9c988-137">Panoramica della programmazione LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c988-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
