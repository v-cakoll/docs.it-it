---
title: Le istruzioni '#Region' e '#End Region' non sono valide nelle espressioni lambda su più righe corpi di metodo
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c41b95da7e3565ae7aaf332fe49361336e79f7c7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303908"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="42934-102">Le istruzioni '#Region' e '#End Region' non sono valide nei corpi di metodi o di espressioni lambda su più righe</span><span class="sxs-lookup"><span data-stu-id="42934-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="42934-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="42934-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="42934-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una procedura.</span><span class="sxs-lookup"><span data-stu-id="42934-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="42934-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="42934-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42934-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="42934-106">To correct this error</span></span>  
  
1. <span data-ttu-id="42934-107">Assicurarsi che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="42934-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="42934-108">Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="42934-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42934-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42934-109">See also</span></span>

- [<span data-ttu-id="42934-110">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="42934-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
