---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032279"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="f2758-102">Comportamento di Nothing con le stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2758-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="f2758-103">Il runtime di Visual Basic e il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] valutare `Nothing` in modo diverso quando si tratta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="f2758-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="f2758-104">Runtime di Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2758-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="f2758-105">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f2758-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="f2758-106">Il runtime di Visual Basic restituisce in genere `Nothing` come una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="f2758-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="f2758-107">Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] non elimina, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="f2758-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2758-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2758-108">See also</span></span>

- [<span data-ttu-id="f2758-109">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f2758-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
