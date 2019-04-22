---
title: << = (operatore) (Visual Basic)
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
ms.openlocfilehash: da2b5ca0b7538d77c3c8d8bc7d45712d656ce63a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829148"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9dc55-102">\<\<= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9dc55-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="9dc55-103">Esegue uno scorrimento a sinistra aritmetico per il valore di una variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="9dc55-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dc55-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="9dc55-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9dc55-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9dc55-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9dc55-106">Required.</span></span> <span data-ttu-id="9dc55-107">Variabile o una proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="9dc55-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="9dc55-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9dc55-108">Required.</span></span> <span data-ttu-id="9dc55-109">Espressione numerica di un tipo di dati che si amplia in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9dc55-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dc55-110">Note</span><span class="sxs-lookup"><span data-stu-id="9dc55-110">Remarks</span></span>  
 <span data-ttu-id="9dc55-111">L'elemento sul lato sinistro del `<<=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="9dc55-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9dc55-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9dc55-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="9dc55-113">Il `<<=` operatore esegue prima di tutto uno spostamento a sinistra aritmetico per il valore della variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="9dc55-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="9dc55-114">L'operatore assegna il risultato dell'operazione tornare a tale variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="9dc55-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="9dc55-115">Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità.</span><span class="sxs-lookup"><span data-stu-id="9dc55-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="9dc55-116">In uno spostamento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati di risultati vengono ignorati e le posizioni dei bit liberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="9dc55-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9dc55-117">Overload</span><span class="sxs-lookup"><span data-stu-id="9dc55-117">Overloading</span></span>  
 <span data-ttu-id="9dc55-118">Il [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9dc55-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9dc55-119">L'overload di `<<` operatore influisce sul comportamento del `<<=` operatore.</span><span class="sxs-lookup"><span data-stu-id="9dc55-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="9dc55-120">Se il codice usi `<<=` in una classe o struttura che esegue l'overload `<<`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9dc55-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9dc55-121">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9dc55-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dc55-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9dc55-122">Example</span></span>  
 <span data-ttu-id="9dc55-123">L'esempio seguente usa il `<<=` operatore per spostare lo schema di bit di un `Integer` variabile da sinistra la quantità specificata e assegna il risultato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="9dc55-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="9dc55-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dc55-124">See also</span></span>

- [<span data-ttu-id="9dc55-125">Operatore <<</span><span class="sxs-lookup"><span data-stu-id="9dc55-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="9dc55-126">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="9dc55-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="9dc55-127">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="9dc55-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="9dc55-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9dc55-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9dc55-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9dc55-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9dc55-130">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="9dc55-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
