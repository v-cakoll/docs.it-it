---
title: 'Procedura: trasformare un frammento di nodo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: 56e9ef6031a5736acfa066ed6c068f954bd5af8d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710817"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="4af42-102">Procedura: trasformare un frammento di nodo</span><span class="sxs-lookup"><span data-stu-id="4af42-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="4af42-103">Quando si trasformano i dati contenuti in un oggetto <xref:System.Xml.XmlDocument> o in un oggetto <xref:System.Xml.XPath.XPathDocument>, le trasformazioni XSLT si applicano a un documento completo.</span><span class="sxs-lookup"><span data-stu-id="4af42-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="4af42-104">In altre parole, se viene passato un nodo diverso dal nodo radice del documento, il processo di trasformazione accederà comunque a tutti i nodi nel documento caricato.</span><span class="sxs-lookup"><span data-stu-id="4af42-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="4af42-105">Per trasformare un frammento di nodo, è necessario creare un oggetto contenente solo il frammento di nodo e passare tale oggetto al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="4af42-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="4af42-106">Procedure</span><span class="sxs-lookup"><span data-stu-id="4af42-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="4af42-107">Per trasformare un frammento di nodo</span><span class="sxs-lookup"><span data-stu-id="4af42-107">To transform a node fragment</span></span>  
  
1. <span data-ttu-id="4af42-108">Creare un oggetto contenente il documento di origine.</span><span class="sxs-lookup"><span data-stu-id="4af42-108">Create an object containing the source document.</span></span>  
  
2. <span data-ttu-id="4af42-109">Individuare il frammento di nodo da trasformare.</span><span class="sxs-lookup"><span data-stu-id="4af42-109">Locate the node fragment you wish to transform.</span></span>  
  
3. <span data-ttu-id="4af42-110">Creare un oggetto separato con il frammento di nodo.</span><span class="sxs-lookup"><span data-stu-id="4af42-110">Create separate object with just the node fragment.</span></span>  
  
4. <span data-ttu-id="4af42-111">Passare il frammento di nodo al metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="4af42-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af42-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4af42-112">Example</span></span>  
 <span data-ttu-id="4af42-113">Nell'esempio seguente un frammento di nodo viene trasformato e il risultato viene visualizzato sulla console.</span><span class="sxs-lookup"><span data-stu-id="4af42-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="4af42-114">Input</span><span class="sxs-lookup"><span data-stu-id="4af42-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="4af42-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="4af42-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="4af42-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="4af42-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="4af42-117">Output</span><span class="sxs-lookup"><span data-stu-id="4af42-117">Output</span></span>  
 <span data-ttu-id="4af42-118">Il titolo del libro è L'uomo di fiducia.</span><span class="sxs-lookup"><span data-stu-id="4af42-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af42-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af42-119">See also</span></span>

- [<span data-ttu-id="4af42-120">Uso della classe XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="4af42-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
