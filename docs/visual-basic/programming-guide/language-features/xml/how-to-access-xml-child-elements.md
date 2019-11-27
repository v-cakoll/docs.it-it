---
title: 'Procedura: accedere agli elementi figlio XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332333"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="ab2ef-102">Procedura: accedere agli elementi figlio XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab2ef-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="ab2ef-103">Questo esempio illustra come usare una proprietà Axis figlio per accedere a tutti gli elementi figlio XML con un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ab2ef-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="ab2ef-104">In particolare, usa la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per ottenere il valore del primo elemento nella raccolta restituita dalla proprietà dell'asse figlio `name`.</span><span class="sxs-lookup"><span data-stu-id="ab2ef-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="ab2ef-105">La proprietà dell'asse figlio `name` ottiene tutti gli elementi figlio denominati `phone` nell'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="ab2ef-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="ab2ef-106">Questo esempio usa anche la proprietà `phone` AXIS Child per accedere a tutti gli elementi figlio denominati `phone` contenuti nell'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="ab2ef-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab2ef-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab2ef-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab2ef-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ab2ef-108">Compiling the Code</span></span>  
 <span data-ttu-id="ab2ef-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab2ef-109">This example requires:</span></span>  
  
- <span data-ttu-id="ab2ef-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="ab2ef-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2ef-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab2ef-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ab2ef-112">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="ab2ef-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="ab2ef-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="ab2ef-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="ab2ef-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab2ef-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="ab2ef-115">XML</span><span class="sxs-lookup"><span data-stu-id="ab2ef-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
