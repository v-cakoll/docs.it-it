---
title: Tipi di dati costanti e letterali (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58fa1e8c6c659c80cd7998a88d07849ea223750f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="77777-102">Tipi di dati costanti e letterali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77777-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="77777-103">Un valore letterale è un valore espresso come se stesso, anziché come valore di una variabile o il risultato di un'espressione, ad esempio il numero 3 oppure la stringa "Hello".</span><span class="sxs-lookup"><span data-stu-id="77777-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="77777-104">Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, anziché una variabile, il cui valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="77777-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="77777-105">Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare tutte le costanti in modo esplicito con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="77777-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="77777-106">Nell'esempio seguente, il tipo di dati `MyByte` in modo esplicito è dichiarato come tipo di dati `Byte`:</span><span class="sxs-lookup"><span data-stu-id="77777-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="77777-107">Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="77777-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="77777-108">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="77777-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="77777-109">Viene eseguito il cast di un valore letterale integer numerico per impostazione predefinita per il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="77777-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="77777-110">Tipo di dati predefinito per numeri a virgola mobile sono `Double`e le parole chiave `True` e `False` specificare un `Boolean` costante.</span><span class="sxs-lookup"><span data-stu-id="77777-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="77777-111">Valori letterali e coercizione di tipi</span><span class="sxs-lookup"><span data-stu-id="77777-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="77777-112">In alcuni casi, è possibile forzare un valore letterale a un tipo di dati specifico. ad esempio, quando si assegna un valore letterale integrale particolarmente elevato a una variabile di tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="77777-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="77777-113">Nell'esempio seguente genera un errore:</span><span class="sxs-lookup"><span data-stu-id="77777-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="77777-114">L'errore deriva dalla rappresentazione del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="77777-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="77777-115">Il `Decimal` tipo di dati può contenere un valore così elevato, ma il valore letterale è rappresentato in modo implicito come una `Long`, che non è possibile.</span><span class="sxs-lookup"><span data-stu-id="77777-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="77777-116">È possibile assegnare un valore letterale in un particolare tipo di dati in due modi: aggiungendo un carattere di tipo o inserendolo in caratteri di contenimento.</span><span class="sxs-lookup"><span data-stu-id="77777-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="77777-117">Un carattere o caratteri di contenimento devono immediatamente precedere e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="77777-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="77777-118">Per correggere l'esempio precedente, è possibile aggiungere il `D` tipo di carattere per il valore letterale, in modo che essere rappresentato come un `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="77777-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="77777-119">Nell'esempio seguente viene illustrato l'uso corretto di caratteri di tipo e che lo contiene:</span><span class="sxs-lookup"><span data-stu-id="77777-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="77777-120">La seguente tabella sono riportati i caratteri che lo contiene e i caratteri di tipo disponibile in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77777-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="77777-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="77777-121">Data type</span></span>|<span data-ttu-id="77777-122">Carattere di inclusione</span><span class="sxs-lookup"><span data-stu-id="77777-122">Enclosing character</span></span>|<span data-ttu-id="77777-123">Carattere di tipo aggiunto</span><span class="sxs-lookup"><span data-stu-id="77777-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="77777-124">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-124">(none)</span></span>|<span data-ttu-id="77777-125">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="77777-126">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-126">(none)</span></span>|<span data-ttu-id="77777-127">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="77777-128">"</span><span class="sxs-lookup"><span data-stu-id="77777-128">"</span></span>|<span data-ttu-id="77777-129">C</span><span class="sxs-lookup"><span data-stu-id="77777-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="77777-130">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="77777-131">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-131">(none)</span></span>|<span data-ttu-id="77777-132">D o @</span><span class="sxs-lookup"><span data-stu-id="77777-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="77777-133">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-133">(none)</span></span>|<span data-ttu-id="77777-134">R o #</span><span class="sxs-lookup"><span data-stu-id="77777-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="77777-135">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-135">(none)</span></span>|<span data-ttu-id="77777-136">I o %</span><span class="sxs-lookup"><span data-stu-id="77777-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="77777-137">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-137">(none)</span></span>|<span data-ttu-id="77777-138">L o &</span><span class="sxs-lookup"><span data-stu-id="77777-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="77777-139">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-139">(none)</span></span>|<span data-ttu-id="77777-140">S</span><span class="sxs-lookup"><span data-stu-id="77777-140">S</span></span>|  
|`Single`|<span data-ttu-id="77777-141">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-141">(none)</span></span>|<span data-ttu-id="77777-142">F o!</span><span class="sxs-lookup"><span data-stu-id="77777-142">F or !</span></span>|  
|`String`|<span data-ttu-id="77777-143">"</span><span class="sxs-lookup"><span data-stu-id="77777-143">"</span></span>|<span data-ttu-id="77777-144">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="77777-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77777-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77777-145">See Also</span></span>  
 [<span data-ttu-id="77777-146">Costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="77777-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="77777-147">Procedura: Dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="77777-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="77777-148">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="77777-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="77777-149">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="77777-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="77777-150">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="77777-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="77777-151">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="77777-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="77777-152">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="77777-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="77777-153">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="77777-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="77777-154">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="77777-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="77777-155">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="77777-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
