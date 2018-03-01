---
title: 'Procedura: dichiarare una costante (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554f659e060087228fb43efd8b9d06103e21e980
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="fc3eb-102">Procedura: dichiarare una costante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc3eb-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="fc3eb-103">Utilizzare il `Const` istruzione per dichiarare una costante e impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="fc3eb-104">Dichiarando una costante, assegnare un nome significativo su un valore.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="fc3eb-105">Dopo aver dichiarata una costante, non può essere modificato o assegnare un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="fc3eb-106">Dichiarare una costante all'interno di una stored procedure o nella sezione delle dichiarazioni di modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="fc3eb-107">Classe o le costanti a livello di struttura sono `Private` per impostazione predefinita, ma possono anche essere dichiarate come `Public`, `Friend`, `Protected`, o `Protected Friend` per il livello di accesso di codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="fc3eb-108">La costante deve avere un nome simbolico valido (le regole sono gli stessi di quelli per la creazione di nomi di variabile) e un'espressione costituita da numerico o stringa costanti e operatori (ma non chiamate di funzioni).</span><span class="sxs-lookup"><span data-stu-id="fc3eb-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="fc3eb-109">Per dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="fc3eb-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="fc3eb-110">Scrivere una dichiarazione che include un identificatore di accesso, il `Const` (parola chiave) e un'espressione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc3eb-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     <span data-ttu-id="fc3eb-111">Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare una costante in modo esplicito specificando un tipo di dati (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="fc3eb-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="fc3eb-112">Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="fc3eb-113">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="fc3eb-114">Per ulteriori informazioni, vedere [costante e tipi di dati letterali](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="fc3eb-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="fc3eb-115">Per dichiarare una costante con un tipo di dati specificata in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="fc3eb-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="fc3eb-116">Scrivere una dichiarazione che include il `As` (parola chiave) e dati espliciti di un tipo, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc3eb-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     <span data-ttu-id="fc3eb-117">È possibile dichiarare più costanti in una singola riga, anche se il codice più leggibile se si dichiara una sola costante per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="fc3eb-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="fc3eb-118">Se si dichiarano più costanti in una singola riga, devono tutti avere lo stesso livello di accesso (`Public`, `Private`, `Friend`, `Protected`, o `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="fc3eb-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="fc3eb-119">Per dichiarare più costanti in una singola riga</span><span class="sxs-lookup"><span data-stu-id="fc3eb-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="fc3eb-120">Le dichiarazioni, separarli con una virgola e uno spazio, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fc3eb-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fc3eb-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc3eb-121">See Also</span></span>  
 [<span data-ttu-id="fc3eb-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="fc3eb-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="fc3eb-123">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="fc3eb-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)  
 <span data-ttu-id="fc3eb-124">[Cenni preliminari sulle costanti](constants-overview.md) [procedura: dichiarare una costante](how-to-declare-a-constant.md) [costanti definite dall'utente](user-defined-constants.md) [tipi di dati costanti e letterali](constant-and-literal-data-types.md) [come: gruppo Valori costanti correlate](how-to-group-related-constant-values-together.md) [Cenni preliminari sulle enumerazioni](enumerations-overview.md) [procedura: dichiarare enumerazioni](how-to-declare-enumerations.md) [procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md) [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md) [procedura: scorrere un'enumerazione](how-to-iterate-through-an-enumeration.md) [procedura: determinare la stringa associata a un valore di enumerazione](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="fc3eb-124">[Constants Overview](constants-overview.md) [How to: Declare A Constant](how-to-declare-a-constant.md) [User-Defined Constants](user-defined-constants.md) [Constant and Literal Data Types](constant-and-literal-data-types.md) [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md) [Enumerations Overview](enumerations-overview.md) [How to: Declare Enumerations](how-to-declare-enumerations.md) [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md) [Enumerations and Name Qualification](enumerations-and-name-qualification.md) [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md) [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md) [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 [<span data-ttu-id="fc3eb-125">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="fc3eb-125">Enumerations Overview</span></span>](enumerations-overview.md)  
 [<span data-ttu-id="fc3eb-126">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="fc3eb-126">Constants Overview</span></span>](constants-overview.md)  
 [<span data-ttu-id="fc3eb-127">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="fc3eb-127">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)  
 [<span data-ttu-id="fc3eb-128">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="fc3eb-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)  
 [<span data-ttu-id="fc3eb-129">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="fc3eb-129">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="fc3eb-130">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="fc3eb-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
