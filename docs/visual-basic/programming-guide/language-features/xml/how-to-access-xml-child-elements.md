---
title: 'Procedura: accedere agli elementi figlio XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d3a708b787ad38f08d4673d4003db839f6cf6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="66da3-102">Procedura: accedere agli elementi figlio XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66da3-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="66da3-103">In questo esempio viene illustrato come utilizzare un elemento figlio di proprietà dell'asse di accesso a tutti gli elementi figlio XML che hanno un nome specificato in un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="66da3-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="66da3-104">In particolare, viene utilizzata la <xref:System.Xml.Linq.XElement.Value%2A> proprietà per ottenere il valore del primo elemento nella raccolta il `name` restituisce proprietà di asse figlio.</span><span class="sxs-lookup"><span data-stu-id="66da3-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="66da3-105">Il `name` proprietà child axis Ottiene tutti gli elementi figlio denominati `phone` nel `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="66da3-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="66da3-106">Questo esempio Usa anche il `phone` proprietà child axis per accedere a tutti gli elementi figlio denominati `phone` in esso contenute il `contact` oggetto.</span><span class="sxs-lookup"><span data-stu-id="66da3-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66da3-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="66da3-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="66da3-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="66da3-108">Compiling the Code</span></span>  
 <span data-ttu-id="66da3-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="66da3-109">This example requires:</span></span>  
  
-   <span data-ttu-id="66da3-110">Un riferimento allo spazio dei nomi <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="66da3-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66da3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66da3-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="66da3-112">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="66da3-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="66da3-113">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="66da3-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="66da3-114">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66da3-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="66da3-115">XML</span><span class="sxs-lookup"><span data-stu-id="66da3-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
