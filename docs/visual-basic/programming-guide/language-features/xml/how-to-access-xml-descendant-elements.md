---
title: 'Procedura: Accesso agli elementi discendenti XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832216"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="b7f96-102">Procedura: Accesso agli elementi discendenti XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7f96-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="b7f96-103">In questo esempio viene illustrato come usare una proprietà axis discendente per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b7f96-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="b7f96-104">In particolare, viene utilizzata la `Value` proprietà da ottenere il valore del primo elemento nella raccolta che il `name` restituisce proprietà axis discendente.</span><span class="sxs-lookup"><span data-stu-id="b7f96-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="b7f96-105">Il `name` proprietà axis descendant Ottiene tutti gli elementi denominati `name` contenuti nel `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b7f96-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="b7f96-106">Questo esempio Usa anche il `phone` proprietà axis discendente per accedere a tutti i discendenti denominati `phone` contenuti nel `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b7f96-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7f96-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7f96-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7f96-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b7f96-108">Compiling the Code</span></span>  
 <span data-ttu-id="b7f96-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7f96-109">This example requires:</span></span>  
  
-   <span data-ttu-id="b7f96-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="b7f96-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f96-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7f96-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b7f96-112">Proprietà axis descendant XML</span><span class="sxs-lookup"><span data-stu-id="b7f96-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="b7f96-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="b7f96-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="b7f96-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7f96-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="b7f96-115">XML</span><span class="sxs-lookup"><span data-stu-id="b7f96-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
