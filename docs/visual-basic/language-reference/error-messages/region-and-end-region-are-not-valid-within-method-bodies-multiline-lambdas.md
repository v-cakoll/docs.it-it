---
title: Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400383"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="8bcd5-102">Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="8bcd5-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="8bcd5-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8bcd5-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="8bcd5-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="8bcd5-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="8bcd5-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="8bcd5-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bcd5-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="8bcd5-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8bcd5-107">Verificare che la procedura precedente sia terminata correttamente con `End Function` un' `End Sub` istruzione o.</span><span class="sxs-lookup"><span data-stu-id="8bcd5-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="8bcd5-108">Verificare che le `#Region` `#End Region` direttive e si trovino nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="8bcd5-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcd5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bcd5-109">See also</span></span>

- [<span data-ttu-id="8bcd5-110">#Region (direttiva)</span><span class="sxs-lookup"><span data-stu-id="8bcd5-110">#Region Directive</span></span>](../directives/region-directive.md)
