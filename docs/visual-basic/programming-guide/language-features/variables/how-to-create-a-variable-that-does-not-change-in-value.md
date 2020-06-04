---
title: 'Procedura: creare una variabile che non cambia di valore'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 04e08784b5cfbdeb6db73b9b00fe9afa201bd06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410516"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="87c30-102">Procedura: creare una variabile che non cambia di valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87c30-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="87c30-103">Il concetto di variabile che non modifica il valore potrebbe sembrare contraddittorio.</span><span class="sxs-lookup"><span data-stu-id="87c30-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="87c30-104">In alcuni casi, tuttavia, una costante non è fattibile ed è utile avere una variabile con un valore fisso.</span><span class="sxs-lookup"><span data-stu-id="87c30-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="87c30-105">In tal caso, è possibile definire una variabile membro con la parola chiave [ReadOnly](../../../language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="87c30-105">In such a case you can define a member variable with the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="87c30-106">Non è possibile usare l' [istruzione Const](../../../language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="87c30-106">You cannot use the [Const Statement](../../../language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="87c30-107">L' `Const` istruzione non accetta il tipo di dati che si desidera utilizzare</span><span class="sxs-lookup"><span data-stu-id="87c30-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="87c30-108">Il valore non è noto in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="87c30-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="87c30-109">Non è possibile calcolare il valore costante in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="87c30-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="87c30-110">Per creare una variabile che non cambia in value</span><span class="sxs-lookup"><span data-stu-id="87c30-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="87c30-111">A livello di modulo, dichiarare una variabile membro con l' [istruzione Dim](../../../language-reference/statements/dim-statement.md)e includere la parola chiave [ReadOnly](../../../language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="87c30-111">At module level, declare a member variable with the [Dim Statement](../../../language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="87c30-112">È possibile specificare `ReadOnly` solo su una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="87c30-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="87c30-113">Ciò significa che è necessario definire la variabile a livello di modulo, al di fuori di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="87c30-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="87c30-114">Se è possibile calcolare il valore in una singola istruzione in fase di compilazione, utilizzare una clausola di inizializzazione nell' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="87c30-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="87c30-115">Seguire la clausola [As](../../../language-reference/statements/as-clause.md) con un segno di uguale ( `=` ), seguito da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="87c30-115">Follow the [As](../../../language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="87c30-116">Verificare che il compilatore possa valutare questa espressione in un valore costante.</span><span class="sxs-lookup"><span data-stu-id="87c30-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="87c30-117">È possibile assegnare un valore a una `ReadOnly` variabile una sola volta.</span><span class="sxs-lookup"><span data-stu-id="87c30-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="87c30-118">Quando si esegue questa operazione, non è possibile modificare il valore di codice.</span><span class="sxs-lookup"><span data-stu-id="87c30-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="87c30-119">Se il valore non è noto in fase di compilazione o non può essere calcolato in fase di compilazione in una singola istruzione, è comunque possibile assegnarlo in fase di esecuzione in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="87c30-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="87c30-120">A tale scopo, è necessario dichiarare la `ReadOnly` variabile a livello di classe o di struttura.</span><span class="sxs-lookup"><span data-stu-id="87c30-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="87c30-121">Nel costruttore della classe o della struttura, calcolare il valore fisso della variabile e assegnarlo alla variabile prima di restituire dal costruttore.</span><span class="sxs-lookup"><span data-stu-id="87c30-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="87c30-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87c30-122">See also</span></span>

- [<span data-ttu-id="87c30-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="87c30-123">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="87c30-124">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="87c30-124">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
