---
title: Corrispondenza di nodi utilizzando XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: 47b0ba7e705ad602825dcca3f24c207362174a4c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289122"
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="936ec-102">Corrispondenza di nodi utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="936ec-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="936ec-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> per determinare se un nodo corrisponde a un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="936ec-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="936ec-104">Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> accetta un'espressione XPath come input e restituisce un oggetto <xref:System.Boolean> che indica se il nodo corrente corrisponde all'espressione XPath o all'oggetto <xref:System.Xml.XPath.XPathExpression> compilato fornito.</span><span class="sxs-lookup"><span data-stu-id="936ec-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="936ec-105">Corrispondenza di nodi</span><span class="sxs-lookup"><span data-stu-id="936ec-105">Matching Nodes</span></span>  
 <span data-ttu-id="936ec-106">Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> restituisce `true` se il nodo corrente corrisponde all'espressione XPath specificata.</span><span class="sxs-lookup"><span data-stu-id="936ec-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="936ec-107">Ad esempio, nel seguente esempio di codice, il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> restituirà `true` se il nodo corrente è l'elemento `b` e se l'elemento `b` presenta un attributo `c`.</span><span class="sxs-lookup"><span data-stu-id="936ec-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="936ec-108">Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> non influisce sullo stato del tipo <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="936ec-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="936ec-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="936ec-109">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="936ec-110">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="936ec-110">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="936ec-111">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="936ec-111">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="936ec-112">Valutazione di espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="936ec-112">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="936ec-113">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="936ec-113">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="936ec-114">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="936ec-114">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="936ec-115">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="936ec-115">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
