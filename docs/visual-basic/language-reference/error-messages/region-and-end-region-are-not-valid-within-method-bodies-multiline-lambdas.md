---
title: "&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide all'interno di espressioni lambda su più righe di corpi di metodo"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593233"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="95e3e-102">&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide all'interno di espressioni lambda corpi/multiline (metodo)</span><span class="sxs-lookup"><span data-stu-id="95e3e-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="95e3e-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="95e3e-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="95e3e-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="95e3e-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="95e3e-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="95e3e-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95e3e-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="95e3e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="95e3e-107">Verificare che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="95e3e-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="95e3e-108">Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="95e3e-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e3e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95e3e-109">See Also</span></span>  
 [<span data-ttu-id="95e3e-110">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="95e3e-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
