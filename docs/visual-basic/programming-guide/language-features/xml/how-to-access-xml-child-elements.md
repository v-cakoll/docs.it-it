---
title: 'Procedura: Accedere agli elementi figlio XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: cd1b0db5305c7879d89cfdfff6cd458d6dea14f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836818"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="191fa-102">Procedura: Accedere agli elementi figlio XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="191fa-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="191fa-103">In questo esempio viene illustrato come utilizzare un elemento figlio proprietà asse a cui accedere tutti gli elementi figlio XML con un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="191fa-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="191fa-104">In particolare, viene utilizzata la <xref:System.Xml.Linq.XElement.Value%2A> proprietà da ottenere il valore del primo elemento nella raccolta che il `name` restituisce proprietà di asse figlio.</span><span class="sxs-lookup"><span data-stu-id="191fa-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="191fa-105">Il `name` proprietà child axis Ottiene tutti gli elementi figlio denominati `phone` nel `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="191fa-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="191fa-106">Questo esempio Usa anche il `phone` proprietà child axis per accedere a tutti gli elementi figlio denominati `phone` contenuti nel `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="191fa-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="191fa-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="191fa-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="191fa-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="191fa-108">Compiling the Code</span></span>  
 <span data-ttu-id="191fa-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="191fa-109">This example requires:</span></span>  
  
-   <span data-ttu-id="191fa-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="191fa-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191fa-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191fa-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="191fa-112">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="191fa-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="191fa-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="191fa-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="191fa-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="191fa-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="191fa-115">XML</span><span class="sxs-lookup"><span data-stu-id="191fa-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
