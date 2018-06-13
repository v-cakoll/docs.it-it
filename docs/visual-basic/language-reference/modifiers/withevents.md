---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596008"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="adc4d-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adc4d-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="adc4d-103">Specifica che uno o più variabili di membro dichiarate fanno riferimento a un'istanza di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="adc4d-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adc4d-104">Note</span><span class="sxs-lookup"><span data-stu-id="adc4d-104">Remarks</span></span>  
 <span data-ttu-id="adc4d-105">Quando una variabile viene definita con `WithEvents`, è possibile specificare in modo dichiarativo che un metodo gestisce gli eventi della variabile utilizzando il `Handles` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="adc4d-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="adc4d-106">È possibile utilizzare `WithEvents` solo a livello di classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="adc4d-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="adc4d-107">Ciò significa che il contesto della dichiarazione per un `WithEvents` variabile deve essere una classe o un modulo e non può essere un file di origine, lo spazio dei nomi, struttura o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="adc4d-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="adc4d-108">Non è possibile utilizzare `WithEvents` su un membro della struttura.</span><span class="sxs-lookup"><span data-stu-id="adc4d-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="adc4d-109">È possibile dichiarare solo variabili singole, non le matrici, ovvero con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="adc4d-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="adc4d-110">Regole</span><span class="sxs-lookup"><span data-stu-id="adc4d-110">Rules</span></span>  
  
-   <span data-ttu-id="adc4d-111">**Tipi di elemento.**</span><span class="sxs-lookup"><span data-stu-id="adc4d-111">**Element Types.**</span></span> <span data-ttu-id="adc4d-112">È necessario dichiarare `WithEvents` le variabili come variabili oggetto in modo che accettino le istanze di classe.</span><span class="sxs-lookup"><span data-stu-id="adc4d-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="adc4d-113">Tuttavia, non è possibile dichiarare come `Object`.</span><span class="sxs-lookup"><span data-stu-id="adc4d-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="adc4d-114">È necessario dichiararle come la classe specifica in grado di generare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="adc4d-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="adc4d-115">Il `WithEvents` modificatore può essere utilizzato in questo contesto: [Dim (istruzione)](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="adc4d-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc4d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adc4d-116">See Also</span></span>  
 [<span data-ttu-id="adc4d-117">Handles</span><span class="sxs-lookup"><span data-stu-id="adc4d-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="adc4d-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="adc4d-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="adc4d-119">Eventi</span><span class="sxs-lookup"><span data-stu-id="adc4d-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
