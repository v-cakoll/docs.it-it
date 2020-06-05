---
title: 'Procedura: creare una nuova variabile'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410529"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="e67c6-102">Procedura: creare una nuova variabile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e67c6-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="e67c6-103">Si crea una variabile con un' [istruzione Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e67c6-103">You create a variable with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="e67c6-104">Per creare una nuova variabile</span><span class="sxs-lookup"><span data-stu-id="e67c6-104">To create a new variable</span></span>

1. <span data-ttu-id="e67c6-105">Dichiarare la variabile in un' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e67c6-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="e67c6-106">Includere le specifiche per le caratteristiche della variabile, ad esempio [private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)o [WithEvents](../../../language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="e67c6-106">Include specifications for the variable's characteristics, such as [Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md), or [WithEvents](../../../language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="e67c6-107">Per altre informazioni, vedere [caratteristiche degli elementi dichiarati](../declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="e67c6-107">For more information, see [Declared Element Characteristics](../declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="e67c6-108">Non è necessaria la `Dim` parola chiave se si usano altre parole chiave nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e67c6-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="e67c6-109">Seguire le specifiche con il nome della variabile, che deve seguire Visual Basic regole e convenzioni.</span><span class="sxs-lookup"><span data-stu-id="e67c6-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="e67c6-110">Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e67c6-110">For more information, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="e67c6-111">Per specificare il tipo di dati della variabile, seguire il nome con la clausola [As](../../../language-reference/statements/as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="e67c6-111">Follow the name with the [As](../../../language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="e67c6-112">Se non si specifica il tipo di dati, verrà utilizzato il valore predefinito: `Object` .</span><span class="sxs-lookup"><span data-stu-id="e67c6-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="e67c6-113">Seguire la `As` clausola con un segno di uguale ( `=` ) e seguire il segno di uguale con il valore iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="e67c6-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="e67c6-114">Visual Basic assegna il valore specificato alla variabile ogni volta che viene eseguita l' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e67c6-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="e67c6-115">Se non si specifica un valore iniziale, Visual Basic assegna il valore iniziale predefinito per il tipo di dati della variabile al momento dell'immissione del codice che contiene l' `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e67c6-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="e67c6-116">Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo la parola chiave [new operator](../../../language-reference/operators/new-operator.md) nella `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="e67c6-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="e67c6-117">Se non si usa `New` , il valore iniziale della variabile è [Nothing](../../../language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="e67c6-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="e67c6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e67c6-118">See also</span></span>

- [<span data-ttu-id="e67c6-119">Variabili</span><span class="sxs-lookup"><span data-stu-id="e67c6-119">Variables</span></span>](index.md)
- [<span data-ttu-id="e67c6-120">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="e67c6-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="e67c6-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="e67c6-121">Declared Element Names</span></span>](../declared-elements/declared-element-names.md)
- [<span data-ttu-id="e67c6-122">Caratteristiche di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="e67c6-122">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="e67c6-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e67c6-123">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="e67c6-124">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="e67c6-124">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="e67c6-125">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="e67c6-125">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="e67c6-126">Option Infer (istruzione)</span><span class="sxs-lookup"><span data-stu-id="e67c6-126">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
