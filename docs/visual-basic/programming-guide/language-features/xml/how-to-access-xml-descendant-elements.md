---
title: 'Procedura: accedere agli elementi discendenti XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347163"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="2a3e7-102">Procedura: accedere agli elementi discendenti XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a3e7-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="2a3e7-103">In questo esempio viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML con un nome specificato e che sono contenuti in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="2a3e7-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="2a3e7-104">In particolare, usa la proprietà `Value` per ottenere il valore del primo elemento nella raccolta restituito dalla proprietà Axis `name` descendant.</span><span class="sxs-lookup"><span data-stu-id="2a3e7-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="2a3e7-105">La proprietà dell'asse discendente `name` ottiene tutti gli elementi denominati `name` contenuti nell'oggetto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="2a3e7-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="2a3e7-106">In questo esempio viene inoltre utilizzata la proprietà axis descendant `phone` per accedere a tutti i discendenti denominati `phone` contenuti nell'oggetto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="2a3e7-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a3e7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a3e7-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="2a3e7-108">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="2a3e7-108">Compile the code</span></span>  
 <span data-ttu-id="2a3e7-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a3e7-109">This example requires:</span></span>  
  
- <span data-ttu-id="2a3e7-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="2a3e7-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3e7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a3e7-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2a3e7-112">Proprietà axis descendant XML</span><span class="sxs-lookup"><span data-stu-id="2a3e7-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="2a3e7-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="2a3e7-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="2a3e7-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a3e7-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="2a3e7-115">XML</span><span class="sxs-lookup"><span data-stu-id="2a3e7-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
