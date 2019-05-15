---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591349"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="af9e5-102">Comportamento di Nothing con le stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af9e5-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="af9e5-103">Il runtime di Visual Basic e .NET Framework valutare `Nothing` in modo diverso quando si tratta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="af9e5-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="af9e5-104">Runtime di Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="af9e5-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="af9e5-105">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="af9e5-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="af9e5-106">Il runtime di Visual Basic restituisce in genere `Nothing` come una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="af9e5-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="af9e5-107">.NET Framework non lo fa, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="af9e5-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9e5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af9e5-108">See also</span></span>

- [<span data-ttu-id="af9e5-109">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="af9e5-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
