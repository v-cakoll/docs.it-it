---
title: Non è accessibile &#39;Main&#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 3398195ef9d503e47ab569ff85cb2a827c4270f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501490"
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="5d036-102">Non è accessibile &#39;Main&#39; metodo con una firma appropriata è stato trovato &#39; &lt;nome&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="5d036-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="5d036-103">Le applicazioni della riga di comando devono avere un `Sub Main` definito.</span><span class="sxs-lookup"><span data-stu-id="5d036-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="5d036-104">`Main` deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.</span><span class="sxs-lookup"><span data-stu-id="5d036-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="5d036-105">**ID errore:** BC30737</span><span class="sxs-lookup"><span data-stu-id="5d036-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d036-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5d036-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5d036-107">Definire un `Public Sub Main` procedure per il progetto.</span><span class="sxs-lookup"><span data-stu-id="5d036-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="5d036-108">Dichiara la classe come `Shared` se e solo se viene definita in una classe.</span><span class="sxs-lookup"><span data-stu-id="5d036-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d036-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d036-109">See also</span></span>
- [<span data-ttu-id="5d036-110">Struttura di un programma Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d036-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="5d036-111">Routine</span><span class="sxs-lookup"><span data-stu-id="5d036-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
