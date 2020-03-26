---
title: Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249526"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="4f146-102">Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento</span><span class="sxs-lookup"><span data-stu-id="4f146-102">First operand in a binary 'If' expression must be nullable or a reference type</span></span>
<span data-ttu-id="4f146-103">Un'espressione `If` può accettare due o tre argomenti.</span><span class="sxs-lookup"><span data-stu-id="4f146-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="4f146-104">Quando si inviano solo due argomenti, il primo argomento deve essere un tipo di riferimento o un tipo di valore nullable.</span><span class="sxs-lookup"><span data-stu-id="4f146-104">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="4f146-105">Se il primo argomento restituisce `Nothing`un valore diverso da , viene restituito il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="4f146-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="4f146-106">Se il primo argomento `Nothing`restituisce , il secondo argomento viene valutato e restituito.</span><span class="sxs-lookup"><span data-stu-id="4f146-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="4f146-107">Ad esempio, il codice `If` seguente contiene due espressioni, una con tre argomenti e una con due argomenti.</span><span class="sxs-lookup"><span data-stu-id="4f146-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="4f146-108">Le espressioni calcolano e restituiscono lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="4f146-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="4f146-109">Le seguenti espressioni causano questo errore:</span><span class="sxs-lookup"><span data-stu-id="4f146-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="4f146-110">**ID errore:** BC33107</span><span class="sxs-lookup"><span data-stu-id="4f146-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f146-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4f146-111">To correct this error</span></span>  
  
- <span data-ttu-id="4f146-112">Se non è possibile modificare il codice in modo che il primo argomento sia un `If` tipo di `If...Then...Else` valore nullable o un tipo di riferimento, prendere in considerazione la conversione in un'espressione a tre argomenti o in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4f146-112">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f146-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f146-113">See also</span></span>

- [<span data-ttu-id="4f146-114">Operatore If</span><span class="sxs-lookup"><span data-stu-id="4f146-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="4f146-115">Istruzione If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="4f146-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="4f146-116">Tipi di valore nullableNullable Value Types</span><span class="sxs-lookup"><span data-stu-id="4f146-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
