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
ms.openlocfilehash: ff7cbb02a9a10dbe11450491e93fd85fd77b44ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370661"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="c36c4-102">\<\<Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c36c4-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="c36c4-103">Esegue uno scorrimento a sinistra aritmetico sul valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c36c4-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c36c4-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="c36c4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c36c4-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="c36c4-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c36c4-106">Required.</span></span> <span data-ttu-id="c36c4-107">Variabile o proprietà di un tipo integrale ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="c36c4-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="c36c4-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c36c4-108">Required.</span></span> <span data-ttu-id="c36c4-109">Espressione numerica di un tipo di dati che viene ampliato a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="c36c4-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c36c4-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="c36c4-110">Remarks</span></span>  
 <span data-ttu-id="c36c4-111">L'elemento sul lato sinistro dell' `<<=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="c36c4-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="c36c4-112">La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="c36c4-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="c36c4-113">L' `<<=` operatore esegue prima uno spostamento aritmetico a sinistra sul valore della variabile o della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c36c4-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="c36c4-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c36c4-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="c36c4-115">I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità.</span><span class="sxs-lookup"><span data-stu-id="c36c4-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="c36c4-116">In uno scorrimento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati del risultato vengono rimossi e le posizioni dei bit sgomberate a destra vengono impostate su zero.</span><span class="sxs-lookup"><span data-stu-id="c36c4-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c36c4-117">Overload</span><span class="sxs-lookup"><span data-stu-id="c36c4-117">Overloading</span></span>  
 <span data-ttu-id="c36c4-118">L' [operatore<< ](left-shift-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="c36c4-118">The [<< Operator](left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c36c4-119">L'overload dell' `<<` operatore influiscono sul comportamento dell' `<<=` operatore.</span><span class="sxs-lookup"><span data-stu-id="c36c4-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="c36c4-120">Se il codice usa `<<=` su una classe o una struttura che esegue l'overload di `<<` , assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="c36c4-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c36c4-121">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c36c4-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c36c4-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="c36c4-122">Example</span></span>  
 <span data-ttu-id="c36c4-123">Nell'esempio seguente viene usato l' `<<=` operatore per spostare lo schema di bit di una `Integer` variabile a sinistra della quantità specificata e assegnare il risultato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c36c4-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="c36c4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c36c4-124">See also</span></span>

- [<span data-ttu-id="c36c4-125">Operatore<< </span><span class="sxs-lookup"><span data-stu-id="c36c4-125"><< Operator</span></span>](left-shift-operator.md)
- [<span data-ttu-id="c36c4-126">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="c36c4-126">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="c36c4-127">Operatori di spostamento bit</span><span class="sxs-lookup"><span data-stu-id="c36c4-127">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="c36c4-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c36c4-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c36c4-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="c36c4-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c36c4-130">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="c36c4-130">Statements</span></span>](../../programming-guide/language-features/statements.md)
