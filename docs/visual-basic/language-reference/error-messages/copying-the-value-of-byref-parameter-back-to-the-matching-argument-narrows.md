---
title: Copiando il valore del parametro 'ByRef' '<parametername>' nell'argomento corrispondente viene eseguita la conversione dal tipo '<typename1>' a '<typename2>', più piccolo
ms.date: 07/20/2015
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
ms.openlocfilehash: bac5f9a88df719bc64a8b0541f65e5912275866e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409751"
---
# <a name="copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument-narrows-from-type-typename1-to-type-typename2"></a><span data-ttu-id="46d54-102">Copiando il valore del parametro 'ByRef' '\<parametername>' nell'argomento corrispondente viene eseguita la conversione dal tipo '\<typename1>' a '\<typename2>', più piccolo</span><span class="sxs-lookup"><span data-stu-id="46d54-102">Copying the value of 'ByRef' parameter '\<parametername>' back to the matching argument narrows from type '\<typename1>' to type '\<typename2>'</span></span>
<span data-ttu-id="46d54-103">Una routine viene chiamata con un argomento che viene ampliato al tipo di parametro corrispondente e la conversione dal parametro all'argomento è più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="46d54-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="46d54-104">Quando si definisce una classe o una struttura, è possibile definire uno o più operatori di conversione per convertire il tipo della classe o della struttura in altri tipi.</span><span class="sxs-lookup"><span data-stu-id="46d54-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="46d54-105">È anche possibile definire operatori di conversione inversi per riconvertire gli altri tipi nel tipo della classe o della struttura originale.</span><span class="sxs-lookup"><span data-stu-id="46d54-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="46d54-106">Quando si usa il tipo di classe o struttura in una chiamata di procedura, Visual Basic possibile usare questi operatori di conversione per convertire il tipo di un argomento nel tipo del parametro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="46d54-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="46d54-107">Se si passa l'argomento [ByRef](../modifiers/byref.md), Visual Basic talvolta copia il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento.</span><span class="sxs-lookup"><span data-stu-id="46d54-107">If you pass the argument [ByRef](../modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="46d54-108">In tal caso, quando la procedura viene restituita, Visual Basic necessario copiare nuovamente il valore della variabile locale nell'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="46d54-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="46d54-109">Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="46d54-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="46d54-110">Tuttavia, se i tipi sono diversi, Visual Basic necessario eseguire la conversione in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="46d54-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="46d54-111">Se uno dei tipi è il tipo della classe o della struttura, Visual Basic necessario convertirlo in e da un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="46d54-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="46d54-112">Se una di queste conversioni viene ampliata, la conversione inversa potrebbe essere più restrittiva.</span><span class="sxs-lookup"><span data-stu-id="46d54-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="46d54-113">**ID errore:** BC32053</span><span class="sxs-lookup"><span data-stu-id="46d54-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46d54-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="46d54-114">To correct this error</span></span>  
  
- <span data-ttu-id="46d54-115">Se possibile, usare un argomento chiamante dello stesso tipo del parametro della routine, in modo che Visual Basic non debba eseguire alcuna conversione.</span><span class="sxs-lookup"><span data-stu-id="46d54-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
- <span data-ttu-id="46d54-116">Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../modifiers/byval.md) invece che `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="46d54-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../modifiers/byval.md) instead of `ByRef`.</span></span>  
  
- <span data-ttu-id="46d54-117">Se è necessario restituire un valore nell'argomento chiamante, definire l'operatore di conversione inverso come più [ampio](../modifiers/widening.md), se possibile.</span><span class="sxs-lookup"><span data-stu-id="46d54-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d54-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46d54-118">See also</span></span>

- [<span data-ttu-id="46d54-119">Procedure</span><span class="sxs-lookup"><span data-stu-id="46d54-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="46d54-120">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="46d54-120">Procedure Parameters and Arguments</span></span>](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="46d54-121">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="46d54-121">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="46d54-122">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="46d54-122">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="46d54-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="46d54-123">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="46d54-124">Procedura: definire un operatore</span><span class="sxs-lookup"><span data-stu-id="46d54-124">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="46d54-125">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="46d54-125">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="46d54-126">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46d54-126">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="46d54-127">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="46d54-127">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
