---
title: 'Procedura: dichiarare una costante (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 8b84ab5e8edebba3048c5cddf723198cf3f28858
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579921"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="8eab9-102">Procedura: dichiarare una costante (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8eab9-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="8eab9-103">Usare l'istruzione `Const` per dichiarare una costante e impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="8eab9-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="8eab9-104">Dichiarando una costante, si assegna un nome significativo a un valore.</span><span class="sxs-lookup"><span data-stu-id="8eab9-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="8eab9-105">Una volta dichiarata una costante, non è possibile modificarla o assegnarle un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="8eab9-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="8eab9-106">Viene dichiarata una costante all'interno di una routine o nella sezione delle dichiarazioni di un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="8eab9-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="8eab9-107">Le costanti a livello di classe o di struttura sono `Private` per impostazione predefinita, ma possono anche essere dichiarate come `Public`, `Friend`, `Protected` o `Protected Friend` per il livello di accesso al codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="8eab9-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="8eab9-108">La costante deve avere un nome simbolico valido (le regole sono le stesse di quelle per la creazione di nomi di variabili) e un'espressione costituita da costanti e operatori numerici o di stringa (ma nessuna chiamata di funzione).</span><span class="sxs-lookup"><span data-stu-id="8eab9-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="8eab9-109">Per dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="8eab9-109">To declare a constant</span></span>  
  
- <span data-ttu-id="8eab9-110">Scrivere una dichiarazione che includa un identificatore di accesso, la parola chiave `Const` e un'espressione, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8eab9-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="8eab9-111">Quando [Option deduce](../../../../visual-basic/language-reference/statements/option-infer-statement.md) è `Off` e [option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare una costante in modo esplicito specificando un tipo di dati (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double` 0 , 1, 2, 3 o 4).</span><span class="sxs-lookup"><span data-stu-id="8eab9-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="8eab9-112">Quando `Option Infer` è `On` o `Option Strict` è `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con una clausola `As`.</span><span class="sxs-lookup"><span data-stu-id="8eab9-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="8eab9-113">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="8eab9-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="8eab9-114">Per altre informazioni, vedere [tipi di dati costanti e letterali](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="8eab9-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="8eab9-115">Per dichiarare una costante con un tipo di dati dichiarato in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="8eab9-115">To declare a constant that has an explicitly stated data type</span></span>  
  
- <span data-ttu-id="8eab9-116">Scrivere una dichiarazione che includa la parola chiave `As` e un tipo di dati esplicito, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8eab9-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="8eab9-117">È possibile dichiarare più costanti su una sola riga, anche se il codice è più leggibile se si dichiara una sola costante per riga.</span><span class="sxs-lookup"><span data-stu-id="8eab9-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="8eab9-118">Se si dichiarano più costanti su una sola riga, devono avere lo stesso livello di accesso (`Public`, `Private`, `Friend`, `Protected` o `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="8eab9-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="8eab9-119">Per dichiarare più costanti su una sola riga</span><span class="sxs-lookup"><span data-stu-id="8eab9-119">To declare multiple constants on a single line</span></span>  
  
- <span data-ttu-id="8eab9-120">Separare le dichiarazioni con una virgola e uno spazio, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8eab9-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8eab9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8eab9-121">See also</span></span>

- [<span data-ttu-id="8eab9-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="8eab9-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="8eab9-123">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="8eab9-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="8eab9-124">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="8eab9-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="8eab9-125">Procedura: Dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="8eab9-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="8eab9-126">Costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="8eab9-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="8eab9-127">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="8eab9-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="8eab9-128">Procedura: Raggruppare i valori delle costanti correlate</span><span class="sxs-lookup"><span data-stu-id="8eab9-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="8eab9-129">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8eab9-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="8eab9-130">Procedura: Dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="8eab9-131">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="8eab9-132">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8eab9-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="8eab9-133">Procedura: Scorrere un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="8eab9-134">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="8eab9-135">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="8eab9-136">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8eab9-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="8eab9-137">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="8eab9-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="8eab9-138">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="8eab9-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="8eab9-139">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8eab9-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="8eab9-140">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="8eab9-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8eab9-141">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8eab9-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
