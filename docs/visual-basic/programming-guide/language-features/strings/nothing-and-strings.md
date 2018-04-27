---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7693e712884a500495e4573900e7d9a049c2879
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="449bc-102">Comportamento di Nothing con le stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="449bc-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="449bc-103">Runtime di Visual Basic e il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] valutare `Nothing` in modo diverso quando si tratta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="449bc-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="449bc-104">Runtime di Visual Basic e .NET Framework</span><span class="sxs-lookup"><span data-stu-id="449bc-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="449bc-105">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="449bc-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="449bc-106">Runtime di Visual Basic in genere valuta `Nothing` come una stringa vuota ("").</span><span class="sxs-lookup"><span data-stu-id="449bc-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="449bc-107">Il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] non, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="449bc-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="449bc-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="449bc-108">See Also</span></span>  
 [<span data-ttu-id="449bc-109">Introduzione alle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="449bc-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
