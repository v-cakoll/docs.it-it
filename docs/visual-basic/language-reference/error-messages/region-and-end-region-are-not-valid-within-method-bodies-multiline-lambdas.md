---
title: Le istruzioni '#Region' e '#End Region' non sono valide nelle espressioni lambda su più righe corpi di metodo
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842707"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="031cb-102">Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="031cb-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="031cb-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="031cb-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="031cb-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una procedura.</span><span class="sxs-lookup"><span data-stu-id="031cb-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="031cb-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="031cb-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="031cb-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="031cb-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="031cb-107">Assicurarsi che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="031cb-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="031cb-108">Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="031cb-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031cb-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="031cb-109">See also</span></span>

- [<span data-ttu-id="031cb-110">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="031cb-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
