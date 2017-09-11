---
title: 'Procedura: dichiarare una costante (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b7fc499336c2b5db3b4d2fe9c0cd11799ea0ad77
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="612c2-102">Procedura: dichiarare una costante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="612c2-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="612c2-103">Utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="612c2-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="612c2-104">Dichiarando una costante, assegnare un nome significativo a un valore.</span><span class="sxs-lookup"><span data-stu-id="612c2-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="612c2-105">Dopo aver dichiarata una costante, non può essere modificato o assegnato un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="612c2-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="612c2-106">Dichiarare una costante all'interno di una routine o nella sezione relativa alle dichiarazioni di modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="612c2-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="612c2-107">Classe o le costanti a livello di struttura sono `Private` per impostazione predefinita, ma possono anche essere dichiarati come `Public`, `Friend`, `Protected`, o `Protected Friend` per il livello appropriato di accesso al codice.</span><span class="sxs-lookup"><span data-stu-id="612c2-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="612c2-108">La costante deve avere un nome simbolico valido (le regole sono identiche a quelle per la creazione di nomi di variabile) e un'espressione costituita da stringhe o numerici costanti e operatori (ma non chiamate di funzioni).</span><span class="sxs-lookup"><span data-stu-id="612c2-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="612c2-109">Per dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="612c2-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="612c2-110">Scrivere una dichiarazione che include un identificatore di accesso, il `Const` (parola chiave) e un'espressione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="612c2-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     <span data-ttu-id="612c2-111">[!code-vb[VbEnumsTask n.&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="612c2-111">[!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span></span>  
  
     <span data-ttu-id="612c2-112">Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare una costante in modo esplicito specificando un tipo di dati (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="612c2-112">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="612c2-113">Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="612c2-113">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="612c2-114">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="612c2-114">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="612c2-115">Per ulteriori informazioni, vedere [costante e tipi di dati letterali](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="612c2-115">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="612c2-116">Per dichiarare una costante con un tipo di dati specificata in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="612c2-116">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="612c2-117">Scrivere una dichiarazione che include il `As` (parola chiave) e un esplicita tipo di dati, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="612c2-117">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     <span data-ttu-id="612c2-118">[!code-vb[9 VbEnumsTask](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="612c2-118">[!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span></span>  
  
     <span data-ttu-id="612c2-119">È possibile dichiarare più costanti in una singola riga, anche se il codice più leggibile se si dichiara una sola costante per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="612c2-119">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="612c2-120">Se si dichiarano più costanti in una singola riga, devono tutti avere lo stesso livello di accesso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="612c2-120">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="612c2-121">Per dichiarare più costanti in una singola riga</span><span class="sxs-lookup"><span data-stu-id="612c2-121">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="612c2-122">Le dichiarazioni, separarli con una virgola e uno spazio, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="612c2-122">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="612c2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="612c2-123">See Also</span></span>  
 <span data-ttu-id="612c2-124">[Const (istruzione)](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-124">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="612c2-125"> [Tipi di dati costanti e letterali](constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-125"> [Constant and Literal Data Types](constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="612c2-126"> [Cenni preliminari sulle costanti](constants-overview.md)
 [come: dichiarare una costante](how-to-declare-a-constant.md)
 [costanti definite dall'utente](user-defined-constants.md)
 [tipi di dati costanti e letterali](constant-and-literal-data-types.md)
 [procedura: raggruppare i valori costanti correlate](how-to-group-related-constant-values-together.md)
 [Cenni preliminari sulle enumerazioni](enumerations-overview.md)
 [come: dichiarare enumerazioni](how-to-declare-enumerations.md)
 [come: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
 [qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
 [procedura: scorrere un'enumerazione](how-to-iterate-through-an-enumeration.md)
 [come: determinare la stringa Associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="612c2-126"> [Constants Overview](constants-overview.md)
 [How to: Declare A Constant](how-to-declare-a-constant.md)
 [User-Defined Constants](user-defined-constants.md)
 [Constant and Literal Data Types](constant-and-literal-data-types.md)
 [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md)
 [Enumerations Overview](enumerations-overview.md)
 [How to: Declare Enumerations](how-to-declare-enumerations.md)
 [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md)
 [Enumerations and Name Qualification](enumerations-and-name-qualification.md)
 [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md)
 [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 <span data-ttu-id="612c2-127">[Cenni preliminari sulle enumerazioni](enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-127">[Enumerations Overview](enumerations-overview.md) </span></span>  
<span data-ttu-id="612c2-128"> [Cenni preliminari sulle costanti](constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-128"> [Constants Overview](constants-overview.md) </span></span>  
<span data-ttu-id="612c2-129"> [Procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-129"> [How to: Declare an Enumeration](how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="612c2-130"> [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-130"> [Enumerations and Name Qualification](enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="612c2-131"> [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="612c2-131"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="612c2-132"> [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="612c2-132"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

