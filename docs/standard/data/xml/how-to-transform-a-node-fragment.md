---
title: 'Procedura: trasformare un frammento di nodo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd35e469a16dc2fdb3a7f4afd89d04f67185cd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568563"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="2890c-102">Procedura: trasformare un frammento di nodo</span><span class="sxs-lookup"><span data-stu-id="2890c-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="2890c-103">Quando si trasformano i dati contenuti in un oggetto <xref:System.Xml.XmlDocument> o in un oggetto <xref:System.Xml.XPath.XPathDocument>, le trasformazioni XSLT si applicano a un documento completo.</span><span class="sxs-lookup"><span data-stu-id="2890c-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="2890c-104">In altre parole, se viene passato un nodo diverso dal nodo radice del documento, il processo di trasformazione accederà comunque a tutti i nodi nel documento caricato.</span><span class="sxs-lookup"><span data-stu-id="2890c-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="2890c-105">Per trasformare un frammento di nodo, è necessario creare un oggetto contenente solo il frammento di nodo e passare tale oggetto al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="2890c-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="2890c-106">Procedure</span><span class="sxs-lookup"><span data-stu-id="2890c-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="2890c-107">Per trasformare un frammento di nodo</span><span class="sxs-lookup"><span data-stu-id="2890c-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="2890c-108">Creare un oggetto contenente il documento di origine.</span><span class="sxs-lookup"><span data-stu-id="2890c-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="2890c-109">Individuare il frammento di nodo da trasformare.</span><span class="sxs-lookup"><span data-stu-id="2890c-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="2890c-110">Creare un oggetto separato con il frammento di nodo.</span><span class="sxs-lookup"><span data-stu-id="2890c-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="2890c-111">Passare il frammento di nodo al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="2890c-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2890c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="2890c-112">Example</span></span>  
 <span data-ttu-id="2890c-113">Nell'esempio seguente un frammento di nodo viene trasformato e il risultato viene visualizzato sulla console.</span><span class="sxs-lookup"><span data-stu-id="2890c-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="2890c-114">Input</span><span class="sxs-lookup"><span data-stu-id="2890c-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="2890c-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="2890c-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="2890c-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="2890c-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="2890c-117">Output</span><span class="sxs-lookup"><span data-stu-id="2890c-117">Output</span></span>  
 <span data-ttu-id="2890c-118">Il titolo del libro è L'uomo di fiducia.</span><span class="sxs-lookup"><span data-stu-id="2890c-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2890c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2890c-119">See Also</span></span>  
 [<span data-ttu-id="2890c-120">Uso della classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="2890c-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
