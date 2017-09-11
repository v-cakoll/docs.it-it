---
title: 'Procedura: dichiarare enumerazioni (Visual Basic) | Documenti di Microsoft'
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 7adaca7e7252ce7165a5fd27b5bc9c049388206c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="633ea-102">Procedura: dichiarare enumerazioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="633ea-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="633ea-103">Per creare un'enumerazione con la `Enum` istruzione nella sezione delle dichiarazioni di una classe o modulo.</span><span class="sxs-lookup"><span data-stu-id="633ea-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="633ea-104">È possibile dichiarare un'enumerazione con un metodo.</span><span class="sxs-lookup"><span data-stu-id="633ea-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="633ea-105">Per specificare il livello appropriato di accesso, utilizzare `Private`, `Protected`, `Friend`, o `Public`.</span><span class="sxs-lookup"><span data-stu-id="633ea-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="633ea-106">Un `Enum` tipo ha un nome, un tipo sottostante e un set di campi, ognuno dei quali rappresenta una costante.</span><span class="sxs-lookup"><span data-stu-id="633ea-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="633ea-107">Il nome deve essere valido [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualificatore.</span><span class="sxs-lookup"><span data-stu-id="633ea-107">The name must be a valid [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualifier.</span></span> <span data-ttu-id="633ea-108">Il tipo sottostante deve essere uno dei tipi integer:`Byte`, `Short`, `Long` o `Integer`.</span><span class="sxs-lookup"><span data-stu-id="633ea-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="633ea-109">Il valore predefinito è `Integer`.</span><span class="sxs-lookup"><span data-stu-id="633ea-109">`Integer` is the default.</span></span> <span data-ttu-id="633ea-110">Le enumerazioni sono sempre fortemente tipizzate e non sono interscambiabili con tipi di numeri integer.</span><span class="sxs-lookup"><span data-stu-id="633ea-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="633ea-111">Le enumerazioni non possono avere valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="633ea-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="633ea-112">Se un'enumerazione viene assegnato un valore a virgola mobile con `Option Strict On`, si verificherà un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="633ea-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="633ea-113">Se `Option Strict` è `Off`, il valore viene convertito automaticamente nel `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="633ea-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="633ea-114">Per informazioni sui nomi e come utilizzare il `Imports` istruzione per evitare la qualifica di nome, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="633ea-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="633ea-115">Per dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="633ea-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="633ea-116">Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` (parola chiave) e un nome valido, come negli esempi seguenti, ognuna delle quali viene dichiarata una differente `Enum`.</span><span class="sxs-lookup"><span data-stu-id="633ea-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     <span data-ttu-id="633ea-117">[!code-vb[VbEnumsTask n.&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="633ea-117">[!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span></span>  
  
2.  <span data-ttu-id="633ea-118">Definire le costanti dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="633ea-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="633ea-119">Per impostazione predefinita, la prima costante nell'enumerazione viene inizializzata a `0`, e le costanti successive vengono inizializzate su un valore di più rispetto alla costante precedente.</span><span class="sxs-lookup"><span data-stu-id="633ea-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="633ea-120">Ad esempio, l'enumerazione seguente `Days`, contiene una costante denominata `Sunday` con il valore `0`, una costante denominata `Monday` con il valore `1`, una costante denominata `Tuesday` con il valore di `2`e così via.</span><span class="sxs-lookup"><span data-stu-id="633ea-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     <span data-ttu-id="633ea-121">[!code-vb[VbEnumsTask n.&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="633ea-121">[!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span></span>  
  
3.  <span data-ttu-id="633ea-122">In modo esplicito, è possibile assegnare valori alle costanti di enumerazione utilizzando un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="633ea-122">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="633ea-123">È possibile assegnare qualsiasi valore intero, inclusi i numeri negativi.</span><span class="sxs-lookup"><span data-stu-id="633ea-123">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="633ea-124">Ad esempio, si consiglia di costanti con i valori minori di zero per rappresentare le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="633ea-124">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="633ea-125">Nell'enumerazione seguente, la costante `Invalid` viene assegnato in modo esplicito il valore `–1`e la costante `Sunday` viene assegnato il valore `0`.</span><span class="sxs-lookup"><span data-stu-id="633ea-125">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="633ea-126">Perché è la prima costante nell'enumerazione, `Saturday` viene inoltre inizializzata sul valore `0`.</span><span class="sxs-lookup"><span data-stu-id="633ea-126">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="633ea-127">Il valore di `Monday` è `1` (uno più il valore di `Sunday`); il valore di `Tuesday` è `2`e così via.</span><span class="sxs-lookup"><span data-stu-id="633ea-127">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     <span data-ttu-id="633ea-128">[!code-vb[VbEnumsTask n.&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="633ea-128">[!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span></span>  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="633ea-129">Per dichiarare un'enumerazione come un tipo esplicito</span><span class="sxs-lookup"><span data-stu-id="633ea-129">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="633ea-130">Specificare il tipo di enumerazione utilizzando il `As` clausola, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="633ea-130">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     <span data-ttu-id="633ea-131">[!code-vb[6 VbEnumsTask](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="633ea-131">[!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633ea-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="633ea-132">See Also</span></span>  
 <span data-ttu-id="633ea-133">[Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-133">[Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="633ea-134"> [Procedura: fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-134"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="633ea-135"> [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-135"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="633ea-136"> [Procedura: determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-136"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="633ea-137"> [Quando utilizzare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-137"> [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span></span>  
<span data-ttu-id="633ea-138"> [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-138"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="633ea-139"> [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="633ea-139"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="633ea-140"> [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="633ea-140"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
