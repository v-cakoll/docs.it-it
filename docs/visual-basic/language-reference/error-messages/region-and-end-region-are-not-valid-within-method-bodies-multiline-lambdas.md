---
title: '&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide nelle espressioni lambda su più righe corpi di metodo'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737215"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="909a9-102">&#39;#Region&#39; e &#39;area #End&#39; istruzioni non sono valide nelle espressioni lambda corpi/su più righe (metodo)</span><span class="sxs-lookup"><span data-stu-id="909a9-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="909a9-103">Il `#Region` blocco deve essere dichiarato a livello di classe, modulo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="909a9-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="909a9-104">Un'area comprimibile può includere una o più procedure, ma non può iniziare o terminare all'interno di una procedura.</span><span class="sxs-lookup"><span data-stu-id="909a9-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="909a9-105">**ID errore:** BC32025</span><span class="sxs-lookup"><span data-stu-id="909a9-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="909a9-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="909a9-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="909a9-107">Assicurarsi che la procedura precedente venga terminata correttamente con un `End Function` o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="909a9-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="909a9-108">Verificare che il `#Region` e `#End Region` direttive sono nello stesso blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="909a9-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909a9-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="909a9-109">See also</span></span>
- [<span data-ttu-id="909a9-110">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="909a9-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
