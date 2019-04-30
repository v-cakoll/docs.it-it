---
title: '>>Operatore = (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982384"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="4c217-102">>> = (operatore) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c217-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="4c217-103">Esegue uno scorrimento aritmetico a destra del valore di una variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c217-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c217-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c217-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="4c217-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4c217-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4c217-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4c217-106">Required.</span></span> <span data-ttu-id="4c217-107">Variabile o una proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="4c217-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="4c217-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4c217-108">Required.</span></span> <span data-ttu-id="4c217-109">Espressione numerica di un tipo di dati che si amplia in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="4c217-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c217-110">Note</span><span class="sxs-lookup"><span data-stu-id="4c217-110">Remarks</span></span>  
 <span data-ttu-id="4c217-111">L'elemento sul lato sinistro del `>>=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="4c217-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4c217-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4c217-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4c217-113">Il `>>=` operatore esegue prima di tutto uno scorrimento aritmetico a destra sul valore della variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c217-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="4c217-114">L'operatore assegna il risultato dell'operazione alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c217-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="4c217-115">Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="4c217-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="4c217-116">In uno scorrimento aritmetico a destra, i bit spostati oltre la posizione del bit più a destra vengono ignorati e il bit più a sinistra viene propagato nelle posizioni dei bit liberate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="4c217-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="4c217-117">Questo significa che se `variableorproperty` ha un valore negativo, le posizioni vuote sono impostate su uno.</span><span class="sxs-lookup"><span data-stu-id="4c217-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="4c217-118">Se `variableorproperty` è positivo, oppure se il tipo di dati è un tipo senza segno, le posizioni vuote vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="4c217-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4c217-119">Overload</span><span class="sxs-lookup"><span data-stu-id="4c217-119">Overloading</span></span>  
 <span data-ttu-id="4c217-120">Il [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="4c217-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4c217-121">L'overload di `>>` operatore influisce sul comportamento del `>>=` operatore.</span><span class="sxs-lookup"><span data-stu-id="4c217-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="4c217-122">Se il codice usi `>>=` in una classe o struttura che esegue l'overload `>>`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="4c217-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4c217-123">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4c217-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c217-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c217-124">Example</span></span>  
 <span data-ttu-id="4c217-125">L'esempio seguente usa il `>>=` operatore per spostare lo schema di bit di un `Integer` variabile di verso destra la quantità specificata e assegna il risultato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="4c217-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="4c217-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c217-126">See also</span></span>

- [<span data-ttu-id="4c217-127">Operatore >></span><span class="sxs-lookup"><span data-stu-id="4c217-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="4c217-128">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="4c217-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="4c217-129">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="4c217-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="4c217-130">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c217-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="4c217-131">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="4c217-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="4c217-132">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="4c217-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
