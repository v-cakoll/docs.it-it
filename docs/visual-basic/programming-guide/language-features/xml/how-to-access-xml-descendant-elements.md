---
title: 'Procedura: accedere agli elementi discendenti XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648486"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="269bc-102">Procedura: accedere agli elementi discendenti XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="269bc-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="269bc-103">In questo esempio viene illustrato come utilizzare una proprietà axis descendant per accedere a tutti gli elementi XML che hanno un nome specificato e che sono contenuti in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="269bc-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="269bc-104">In particolare, viene utilizzata la `Value` proprietà per ottenere il valore del primo elemento nella raccolta la `name` restituisce proprietà axis descendant.</span><span class="sxs-lookup"><span data-stu-id="269bc-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="269bc-105">Il `name` proprietà axis descendant Ottiene tutti gli elementi denominati `name` in esso contenute il `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="269bc-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="269bc-106">Questo esempio Usa anche il `phone` proprietà axis descendant per accedere a tutti i discendenti denominati `phone` in esso contenute il `contacts` oggetto.</span><span class="sxs-lookup"><span data-stu-id="269bc-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="269bc-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="269bc-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="269bc-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="269bc-108">Compiling the Code</span></span>  
 <span data-ttu-id="269bc-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="269bc-109">This example requires:</span></span>  
  
-   <span data-ttu-id="269bc-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="269bc-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269bc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="269bc-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="269bc-112">Proprietà axis descendant XML</span><span class="sxs-lookup"><span data-stu-id="269bc-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="269bc-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="269bc-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="269bc-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="269bc-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="269bc-115">XML</span><span class="sxs-lookup"><span data-stu-id="269bc-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
