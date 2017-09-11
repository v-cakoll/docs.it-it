---
title: Tipi di dati costanti e letterali (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 29a997ee0dd847e8505d1a5c24cacfdfdb0a42cc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="5521c-102">Tipi di dati costanti e letterali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5521c-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="5521c-103">Un valore letterale è un valore che viene espresso come stesso anziché come valore della variabile o il risultato di un'espressione, ad esempio il numero 3 oppure la stringa "Hello".</span><span class="sxs-lookup"><span data-stu-id="5521c-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="5521c-104">Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, anziché una variabile, il cui valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="5521c-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="5521c-105">Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare tutte le costanti in modo esplicito con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5521c-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="5521c-106">Nell'esempio seguente, il tipo di dati `MyByte` viene dichiarato esplicitamente come tipo di dati `Byte`:</span><span class="sxs-lookup"><span data-stu-id="5521c-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 <span data-ttu-id="5521c-107">[!code-vb[VbVbalrConstants n.&1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5521c-107">[!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="5521c-108">Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="5521c-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="5521c-109">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="5521c-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="5521c-110">Viene eseguito il cast di un valore letterale integer numerico per impostazione predefinita per il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5521c-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="5521c-111">Tipo di dati predefinito per numeri a virgola mobile sono `Double`e le parole chiave `True` e `False` specificare un `Boolean` costante.</span><span class="sxs-lookup"><span data-stu-id="5521c-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="5521c-112">Coercizione di tipi e valori letterali</span><span class="sxs-lookup"><span data-stu-id="5521c-112">Literals and Type Coercion</span></span>  
 <span data-ttu-id="5521c-113">In alcuni casi, potrebbe essere necessario forzare un valore letterale a un tipo di dati specifico. ad esempio, quando si assegna un valore letterale integrale particolarmente elevato a una variabile di tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5521c-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="5521c-114">Nell'esempio seguente genera un errore:</span><span class="sxs-lookup"><span data-stu-id="5521c-114">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="5521c-115">L'errore deriva dalla rappresentazione del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="5521c-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="5521c-116">Il `Decimal` tipo di dati può contenere un valore così elevato, ma il valore letterale è rappresentato in modo implicito come una `Long`, che non può.</span><span class="sxs-lookup"><span data-stu-id="5521c-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="5521c-117">È possibile assegnare un valore letterale in un particolare tipo di dati in due modi: aggiungendovi un carattere di tipo o inserendolo all'interno di caratteri di contenimento.</span><span class="sxs-lookup"><span data-stu-id="5521c-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="5521c-118">Un carattere di tipo caratteri di contenimento devono immediatamente precedere o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="5521c-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="5521c-119">Per correggere l'esempio precedente, è possibile aggiungere il `D` tipo di carattere per il valore letterale, in modo che essere rappresentato come un `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="5521c-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 <span data-ttu-id="5521c-120">[!code-vb[VbVbalrConstants n.&2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5521c-120">[!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="5521c-121">Nell'esempio seguente viene illustrato l'uso corretto di caratteri di tipo e che lo contiene:</span><span class="sxs-lookup"><span data-stu-id="5521c-121">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 <span data-ttu-id="5521c-122">[!code-vb[VbVbalrConstants n.&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5521c-122">[!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="5521c-123">Nella tabella seguente, i caratteri di inclusione e tipo di caratteri disponibili in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="5521c-123">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|<span data-ttu-id="5521c-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5521c-124">Data type</span></span>|<span data-ttu-id="5521c-125">Carattere di inclusione</span><span class="sxs-lookup"><span data-stu-id="5521c-125">Enclosing character</span></span>|<span data-ttu-id="5521c-126">Carattere di tipo aggiunto</span><span class="sxs-lookup"><span data-stu-id="5521c-126">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="5521c-127">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-127">(none)</span></span>|<span data-ttu-id="5521c-128">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-128">(none)</span></span>|  
|`Byte`|<span data-ttu-id="5521c-129">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-129">(none)</span></span>|<span data-ttu-id="5521c-130">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-130">(none)</span></span>|  
|`Char`|<span data-ttu-id="5521c-131">"</span><span class="sxs-lookup"><span data-stu-id="5521c-131">"</span></span>|<span data-ttu-id="5521c-132">C</span><span class="sxs-lookup"><span data-stu-id="5521c-132">C</span></span>|  
|`Date`|#|<span data-ttu-id="5521c-133">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-133">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="5521c-134">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-134">(none)</span></span>|<span data-ttu-id="5521c-135">D o @</span><span class="sxs-lookup"><span data-stu-id="5521c-135">D or @</span></span>|  
|`Double`|<span data-ttu-id="5521c-136">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-136">(none)</span></span>|<span data-ttu-id="5521c-137">R o</span><span class="sxs-lookup"><span data-stu-id="5521c-137">R or</span></span> #|  
|`Integer`|<span data-ttu-id="5521c-138">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-138">(none)</span></span>|<span data-ttu-id="5521c-139">Non è o %</span><span class="sxs-lookup"><span data-stu-id="5521c-139">I or %</span></span>|  
|`Long`|<span data-ttu-id="5521c-140">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-140">(none)</span></span>|<span data-ttu-id="5521c-141">L o /</span><span class="sxs-lookup"><span data-stu-id="5521c-141">L or &</span></span>|  
|`Short`|<span data-ttu-id="5521c-142">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-142">(none)</span></span>|<span data-ttu-id="5521c-143">S</span><span class="sxs-lookup"><span data-stu-id="5521c-143">S</span></span>|  
|`Single`|<span data-ttu-id="5521c-144">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-144">(none)</span></span>|<span data-ttu-id="5521c-145">F o!</span><span class="sxs-lookup"><span data-stu-id="5521c-145">F or !</span></span>|  
|`String`|<span data-ttu-id="5521c-146">"</span><span class="sxs-lookup"><span data-stu-id="5521c-146">"</span></span>|<span data-ttu-id="5521c-147">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="5521c-147">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5521c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5521c-148">See Also</span></span>  
 <span data-ttu-id="5521c-149">[Costanti definite dall'utente](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-149">[User-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span></span>  
<span data-ttu-id="5521c-150"> [Procedura: dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-150"> [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span></span>  
<span data-ttu-id="5521c-151"> [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-151"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="5521c-152"> [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-152"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="5521c-153"> [Istruzione Option Explicit](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-153"> [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="5521c-154"> [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-154"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="5521c-155"> [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-155"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="5521c-156"> [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-156"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="5521c-157"> [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="5521c-157"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="5521c-158"> [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="5521c-158"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
