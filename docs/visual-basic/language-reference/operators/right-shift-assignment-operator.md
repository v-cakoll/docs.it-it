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
ms.openlocfilehash: 08d4e251a96ca387a709319e752351db6825d9e8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701351"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a8763-102">Operatore > > = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8763-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="a8763-103">Esegue uno spostamento a destra aritmetico sul valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8763-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8763-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8763-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="a8763-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a8763-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a8763-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a8763-106">Required.</span></span> <span data-ttu-id="a8763-107">Variabile o proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="a8763-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="a8763-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a8763-108">Required.</span></span> <span data-ttu-id="a8763-109">Espressione numerica di un tipo di dati che viene ampliato a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a8763-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8763-110">Note</span><span class="sxs-lookup"><span data-stu-id="a8763-110">Remarks</span></span>  
 <span data-ttu-id="a8763-111">L'elemento sul lato sinistro dell'operatore `>>=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a8763-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a8763-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a8763-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a8763-113">L'operatore `>>=` esegue prima di tutto un passaggio aritmetico a destra sul valore della variabile o della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8763-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="a8763-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8763-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="a8763-115">I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="a8763-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="a8763-116">In uno spostamento a destra aritmetico i bit spostati oltre la posizione del bit più a destra vengono eliminati e il bit più a sinistra viene propagato nelle posizioni dei bit sgomberate a sinistra.</span><span class="sxs-lookup"><span data-stu-id="a8763-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="a8763-117">Ciò significa che se `variableorproperty` ha un valore negativo, le posizioni sgomberate sono impostate su uno.</span><span class="sxs-lookup"><span data-stu-id="a8763-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="a8763-118">Se `variableorproperty` è positivo o se il tipo di dati è un tipo senza segno, le posizioni sgomberate vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="a8763-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a8763-119">Overload</span><span class="sxs-lookup"><span data-stu-id="a8763-119">Overloading</span></span>  
 <span data-ttu-id="a8763-120">L' [operatore > >](../../../visual-basic/language-reference/operators/right-shift-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="a8763-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a8763-121">L'overload dell'operatore `>>` influiscono sul comportamento dell'operatore `>>=`.</span><span class="sxs-lookup"><span data-stu-id="a8763-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="a8763-122">Se il codice USA `>>=` su una classe o una struttura che esegue l'overload `>>`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="a8763-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a8763-123">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a8763-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8763-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8763-124">Example</span></span>  
 <span data-ttu-id="a8763-125">Nell'esempio seguente viene usato l'operatore `>>=` per spostare lo schema di bit di una variabile `Integer` a destra in base alla quantità specificata e assegnare il risultato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="a8763-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="a8763-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8763-126">See also</span></span>

- [<span data-ttu-id="a8763-127">Operatore >></span><span class="sxs-lookup"><span data-stu-id="a8763-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="a8763-128">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="a8763-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="a8763-129">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="a8763-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="a8763-130">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8763-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a8763-131">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a8763-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a8763-132">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="a8763-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
