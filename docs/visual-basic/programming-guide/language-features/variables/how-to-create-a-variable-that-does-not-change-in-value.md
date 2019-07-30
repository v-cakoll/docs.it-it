---
title: 'Procedura: Creare una variabile che non cambia in value (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d201e95463dd0431825fee03ebfd340ac80cc552
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630892"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="3b783-102">Procedura: Creare una variabile che non cambia in value (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b783-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="3b783-103">Il concetto di variabile che non modifica il valore potrebbe sembrare contraddittorio.</span><span class="sxs-lookup"><span data-stu-id="3b783-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="3b783-104">In alcuni casi, tuttavia, una costante non è fattibile ed è utile avere una variabile con un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="3b783-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="3b783-105">In tal caso, è possibile definire una variabile membro con la parola chiave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="3b783-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="3b783-106">Non è possibile usare l' [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b783-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="3b783-107">L' `Const` istruzione non accetta il tipo di dati che si desidera utilizzare</span><span class="sxs-lookup"><span data-stu-id="3b783-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="3b783-108">Il valore non è noto in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="3b783-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="3b783-109">Non è possibile calcolare il valore costante in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="3b783-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="3b783-110">Per creare una variabile che non cambia in value</span><span class="sxs-lookup"><span data-stu-id="3b783-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="3b783-111">A livello di modulo, dichiarare una variabile membro con l' [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere la parola chiave [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="3b783-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="3b783-112">È possibile specificare `ReadOnly` solo su una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="3b783-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="3b783-113">Ciò significa che è necessario definire la variabile a livello di modulo, al di fuori di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="3b783-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="3b783-114">Se è possibile calcolare il valore in una singola istruzione in fase di compilazione, utilizzare una clausola di inizializzazione `Dim` nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="3b783-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="3b783-115">Seguire la clausola [As](../../../../visual-basic/language-reference/statements/as-clause.md) con un segno di uguale`=`(), seguito da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3b783-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="3b783-116">Verificare che il compilatore possa valutare questa espressione in un valore costante.</span><span class="sxs-lookup"><span data-stu-id="3b783-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="3b783-117">È possibile assegnare un valore a una `ReadOnly` variabile una sola volta.</span><span class="sxs-lookup"><span data-stu-id="3b783-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="3b783-118">Quando si esegue questa operazione, non è possibile modificare il valore di codice.</span><span class="sxs-lookup"><span data-stu-id="3b783-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="3b783-119">Se il valore non è noto in fase di compilazione o non può essere calcolato in fase di compilazione in una singola istruzione, è comunque possibile assegnarlo in fase di esecuzione in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="3b783-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="3b783-120">A tale scopo, è necessario dichiarare la `ReadOnly` variabile a livello di classe o di struttura.</span><span class="sxs-lookup"><span data-stu-id="3b783-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="3b783-121">Nel costruttore della classe o della struttura, calcolare il valore fisso della variabile e assegnarlo alla variabile prima di restituire dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="3b783-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b783-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b783-122">See also</span></span>

- [<span data-ttu-id="3b783-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="3b783-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="3b783-124">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="3b783-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
