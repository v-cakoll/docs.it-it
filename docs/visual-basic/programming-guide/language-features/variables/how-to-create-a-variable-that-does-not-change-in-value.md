---
title: 'Procedura: Creare una variabile che non cambia di valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 7180e5141572d219ed02c57103e9d4b80cde536e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342934"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="f8931-102">Procedura: Creare una variabile che non cambia di valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8931-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="f8931-103">Il concetto di una variabile che non cambia il relativo valore potrebbe sembrare contraddittorio.</span><span class="sxs-lookup"><span data-stu-id="f8931-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="f8931-104">Ma esistono situazioni in cui una costante non è fattibile e risulta utile avere una variabile con un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="f8931-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="f8931-105">In tal caso è possibile definire una variabile membro con il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="f8931-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="f8931-106">Non è possibile usare la [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) dichiarare e assegnare un valore costante nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8931-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
-   <span data-ttu-id="f8931-107">Il `Const` istruzione non accetta il tipo di dati da usare</span><span class="sxs-lookup"><span data-stu-id="f8931-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
-   <span data-ttu-id="f8931-108">Non si conosce il valore in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="f8931-108">You do not know the value at compile time</span></span>  
  
-   <span data-ttu-id="f8931-109">È in grado di calcolare il valore costante in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="f8931-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="f8931-110">Per creare una variabile che non cambia di valore</span><span class="sxs-lookup"><span data-stu-id="f8931-110">To create a variable that does not change in value</span></span>  
  
1. <span data-ttu-id="f8931-111">A livello di modulo, dichiarare una variabile membro con il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere le [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="f8931-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="f8931-112">È possibile specificare `ReadOnly` solo su una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="f8931-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="f8931-113">Ciò significa che è necessario definire la variabile a livello di modulo, di fuori di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="f8931-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2. <span data-ttu-id="f8931-114">Se è possibile calcolare il valore in un'unica istruzione in fase di compilazione, usare una clausola di inizializzazione nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="f8931-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="f8931-115">Seguire le [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola con un segno di uguale (`=`), seguita da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f8931-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="f8931-116">Assicurarsi che il compilatore può valutare questa espressione a un valore costante.</span><span class="sxs-lookup"><span data-stu-id="f8931-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="f8931-117">È possibile assegnare un valore per un `ReadOnly` variabile una sola volta.</span><span class="sxs-lookup"><span data-stu-id="f8931-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="f8931-118">Una volta in questo caso, nessun codice mai possibile modificarne il valore.</span><span class="sxs-lookup"><span data-stu-id="f8931-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="f8931-119">Se non si conosce il valore in fase di compilazione o non è possibile calcolare in fase di compilazione in un'unica istruzione, è possibile assegnarla ancora in fase di esecuzione in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="f8931-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="f8931-120">A tale scopo, è necessario dichiarare il `ReadOnly` variabili a livello di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="f8931-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="f8931-121">Nel costruttore per quella classe o struttura, calcolare il valore della variabile fissa e assegnarlo alla variabile prima della restituzione dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="f8931-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8931-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8931-122">See also</span></span>

- [<span data-ttu-id="f8931-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="f8931-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="f8931-124">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="f8931-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
