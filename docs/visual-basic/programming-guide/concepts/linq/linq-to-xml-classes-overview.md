---
title: LINQ to XML panoramica delle classi (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f22f1b7e4f94acda3a9279baf92fbce0840e55ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-classes-overview-visual-basic"></a><span data-ttu-id="8fcd2-102">LINQ to XML panoramica delle classi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fcd2-102">LINQ to XML Classes Overview (Visual Basic)</span></span>
<span data-ttu-id="8fcd2-103">In questo argomento viene fornito un elenco delle classi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] disponibili nello spazio dei nomi <xref:System.Xml.Linq>, con una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="8fcd2-104">Classi LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="8fcd2-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="8fcd2-105">Classe XAttribute</span><span class="sxs-lookup"><span data-stu-id="8fcd2-105">XAttribute Class</span></span>  
 <span data-ttu-id="8fcd2-106"><xref:System.Xml.Linq.XAttribute> rappresenta un attributo XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="8fcd2-107">Per informazioni dettagliate ed esempi, vedere [Cenni preliminari sulla classe XAttribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-107">For detailed information and examples, see [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="8fcd2-108">Classe XCData</span><span class="sxs-lookup"><span data-stu-id="8fcd2-108">XCData Class</span></span>  
 <span data-ttu-id="8fcd2-109"><xref:System.Xml.Linq.XCData> rappresenta un nodo di testo CDAT.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="8fcd2-110">Classe XComment</span><span class="sxs-lookup"><span data-stu-id="8fcd2-110">XComment Class</span></span>  
 <span data-ttu-id="8fcd2-111"><xref:System.Xml.Linq.XComment> rappresenta un commento XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="8fcd2-112">Classe XContainer</span><span class="sxs-lookup"><span data-stu-id="8fcd2-112">XContainer Class</span></span>  
 <span data-ttu-id="8fcd2-113"><xref:System.Xml.Linq.XContainer> è una classe di base astratta per tutti i nodi che possono avere nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="8fcd2-114">Le seguenti classi derivano dalla classe <xref:System.Xml.Linq.XContainer>:</span><span class="sxs-lookup"><span data-stu-id="8fcd2-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="8fcd2-115">Classe XDeclaration</span><span class="sxs-lookup"><span data-stu-id="8fcd2-115">XDeclaration Class</span></span>  
 <span data-ttu-id="8fcd2-116"><xref:System.Xml.Linq.XDeclaration> rappresenta una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-116"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="8fcd2-117">Una dichiarazione XML viene usata per dichiarare la versione XML e la codifica di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-117">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="8fcd2-118">Inoltre, una dichiarazione XML specifica se il documento XML è autonomo o meno.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-118">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="8fcd2-119">Se il documento è autonomo non sono presenti dichiarazioni di markup esterne in una DTD esterna o in un'entità parametro esterna a cui è fatto riferimento dal subset interno.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-119">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="8fcd2-120">Classe XDocument</span><span class="sxs-lookup"><span data-stu-id="8fcd2-120">XDocument Class</span></span>  
 <span data-ttu-id="8fcd2-121"><xref:System.Xml.Linq.XDocument> rappresenta un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-121"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="8fcd2-122">Per informazioni dettagliate ed esempi, vedere [Cenni preliminari sulla classe XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-122">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="8fcd2-123">Classe XDocumentType</span><span class="sxs-lookup"><span data-stu-id="8fcd2-123">XDocumentType Class</span></span>  
 <span data-ttu-id="8fcd2-124"><xref:System.Xml.Linq.XDocumentType> rappresenta una definizione DTD (Document Type Definition) XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-124"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="8fcd2-125">Classe XElement</span><span class="sxs-lookup"><span data-stu-id="8fcd2-125">XElement Class</span></span>  
 <span data-ttu-id="8fcd2-126"><xref:System.Xml.Linq.XElement> rappresenta un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-126"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="8fcd2-127">Per informazioni dettagliate ed esempi, vedere [Cenni preliminari sulla classe XElement (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-127">For detailed information and examples, see [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="8fcd2-128">Classe XName</span><span class="sxs-lookup"><span data-stu-id="8fcd2-128">XName Class</span></span>  
 <span data-ttu-id="8fcd2-129"><xref:System.Xml.Linq.XName> rappresenta nomi di elementi (<xref:System.Xml.Linq.XElement>) e attributi (<xref:System.Xml.Linq.XAttribute>).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-129"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="8fcd2-130">Per informazioni dettagliate ed esempi, vedere [Cenni preliminari sulla classe XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8fcd2-130">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="8fcd2-131"> è progettato per semplificare il più possibile i nomi XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-131"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="8fcd2-132">Essendo molto complessi, i nomi XML vengono spesso considerati un argomento avanzato in XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-132">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="8fcd2-133">In effetti questa complessità non deriva dagli spazi dei nomi, utilizzati regolarmente dagli sviluppatori nella programmazione, ma dai prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-133">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="8fcd2-134">I prefissi di spazio dei nomi possono risultare utili per ridurre le sequenze di tasti richieste durante l'input XML o per migliorare la leggibilità di XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-134">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="8fcd2-135">Tuttavia, i prefissi rappresentano spesso solo una scelta rapida per utilizzare lo spazio dei nomi XML completo e nella maggior parte dei casi non sono necessari.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-135">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> <span data-ttu-id="8fcd2-136">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] i nomi XML vengono semplificati risolvendo tutti i prefissi nello spazio dei nomi XML corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-136">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="8fcd2-137">Se necessari, i prefissi sono disponibili tramite il metodo <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-137">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="8fcd2-138">Se è necessario, è possibile controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-138">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="8fcd2-139">In alcune circostanze, se si usano altri sistemi XML, ad esempio XSLT o XAML, è necessario controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-139">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="8fcd2-140">Ad esempio se in un'espressione XPath incorporata in un foglio di stile XSLT vengono usati i prefissi di spazio dei nomi, è necessario assicurarsi che il documento XML venga serializzato con prefissi di spazio dei nomi corrispondenti a quelli usati nell'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-140">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="8fcd2-141">Classe XNamespace</span><span class="sxs-lookup"><span data-stu-id="8fcd2-141">XNamespace Class</span></span>  
 <span data-ttu-id="8fcd2-142"><xref:System.Xml.Linq.XNamespace> rappresenta uno spazio dei nomi per <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-142"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="8fcd2-143">Gli spazi dei nomi sono un componente di <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-143">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="8fcd2-144">Classe XNode</span><span class="sxs-lookup"><span data-stu-id="8fcd2-144">XNode Class</span></span>  
 <span data-ttu-id="8fcd2-145"><xref:System.Xml.Linq.XNode> è una classe astratta che rappresenta i nodi di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-145"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="8fcd2-146">Le seguenti classi derivano dalla classe <xref:System.Xml.Linq.XNode>:</span><span class="sxs-lookup"><span data-stu-id="8fcd2-146">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="8fcd2-147">Classe XNodeDocumentOrderComparer</span><span class="sxs-lookup"><span data-stu-id="8fcd2-147">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="8fcd2-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> fornisce funzionalità per confrontare nodi per rilevare l'ordine del documento.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-148"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="8fcd2-149">Classe XNodeEqualityComparer</span><span class="sxs-lookup"><span data-stu-id="8fcd2-149">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="8fcd2-150"><xref:System.Xml.Linq.XNodeEqualityComparer> fornisce funzionalità per confrontare nodi per rilevare l'uguaglianza di valori.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-150"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="8fcd2-151">Classe XObject</span><span class="sxs-lookup"><span data-stu-id="8fcd2-151">XObject Class</span></span>  
 <span data-ttu-id="8fcd2-152"><xref:System.Xml.Linq.XObject> è una classe di base astratta di <xref:System.Xml.Linq.XNode> e <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-152"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="8fcd2-153">Fornisce funzionalità di annotazione ed evento.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-153">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="8fcd2-154">Classe XObjectChange</span><span class="sxs-lookup"><span data-stu-id="8fcd2-154">XObjectChange Class</span></span>  
 <span data-ttu-id="8fcd2-155"><xref:System.Xml.Linq.XObjectChange> specifica il tipo di evento quando viene generato un evento per <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-155"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="8fcd2-156">Classe XObjectChangeEventArgs</span><span class="sxs-lookup"><span data-stu-id="8fcd2-156">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="8fcd2-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> fornisce i dati per gli eventi <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-157"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="8fcd2-158">Classe XProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="8fcd2-158">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="8fcd2-159"><xref:System.Xml.Linq.XProcessingInstruction> rappresenta un'istruzione di elaborazione XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-159"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="8fcd2-160">Un'istruzione di elaborazione comunica informazioni a un'applicazione che elabora l'XML.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-160">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="8fcd2-161">Classe XText</span><span class="sxs-lookup"><span data-stu-id="8fcd2-161">XText Class</span></span>  
 <span data-ttu-id="8fcd2-162"><xref:System.Xml.Linq.XText> rappresenta un nodo di testo.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-162"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="8fcd2-163">Nella maggior parte dei casi non è necessario usare questa classe,</span><span class="sxs-lookup"><span data-stu-id="8fcd2-163">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="8fcd2-164">che viene usata principalmente per contenuto misto.</span><span class="sxs-lookup"><span data-stu-id="8fcd2-164">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fcd2-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fcd2-165">See Also</span></span>  
 [<span data-ttu-id="8fcd2-166">LINQ to XML Panoramica della programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fcd2-166">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
