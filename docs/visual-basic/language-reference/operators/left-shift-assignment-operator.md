---
title: Operatore <<=
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350948"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2af2e-102">Operatore \<\<= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2af2e-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="2af2e-103">Esegue uno scorrimento a sinistra aritmetico sul valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="2af2e-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2af2e-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="2af2e-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2af2e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2af2e-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="2af2e-106">Required.</span></span> <span data-ttu-id="2af2e-107">Variabile o proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="2af2e-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="2af2e-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="2af2e-108">Required.</span></span> <span data-ttu-id="2af2e-109">Espressione numerica di un tipo di dati che viene ampliato a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2af2e-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2af2e-110">Note</span><span class="sxs-lookup"><span data-stu-id="2af2e-110">Remarks</span></span>  
 <span data-ttu-id="2af2e-111">L'elemento sul lato sinistro dell'operatore `<<=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="2af2e-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2af2e-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="2af2e-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2af2e-113">L'operatore `<<=` esegue innanzitutto uno spostamento a sinistra aritmetico sul valore della variabile o della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2af2e-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="2af2e-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="2af2e-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="2af2e-115">I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="2af2e-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="2af2e-116">In uno scorrimento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati del risultato vengono rimossi e le posizioni dei bit sgomberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="2af2e-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2af2e-117">Overload</span><span class="sxs-lookup"><span data-stu-id="2af2e-117">Overloading</span></span>  
 <span data-ttu-id="2af2e-118">L' [operatore < <](../../../visual-basic/language-reference/operators/left-shift-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="2af2e-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2af2e-119">L'overload dell'operatore `<<` influiscono sul comportamento dell'operatore `<<=`.</span><span class="sxs-lookup"><span data-stu-id="2af2e-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="2af2e-120">Se il codice USA `<<=` su una classe o una struttura che esegue l'overload di `<<`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="2af2e-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2af2e-121">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2af2e-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2af2e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="2af2e-122">Example</span></span>  
 <span data-ttu-id="2af2e-123">Nell'esempio seguente viene usato l'operatore `<<=` per spostare lo schema di bit di una variabile `Integer` a sinistra della quantità specificata e assegnare il risultato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="2af2e-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="2af2e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2af2e-124">See also</span></span>

- [<span data-ttu-id="2af2e-125">Operatore <<</span><span class="sxs-lookup"><span data-stu-id="2af2e-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="2af2e-126">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="2af2e-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2af2e-127">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="2af2e-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="2af2e-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2af2e-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2af2e-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="2af2e-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2af2e-130">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="2af2e-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
