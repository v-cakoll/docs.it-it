---
title: Costanti (Visual Basic) definiti dall&quot;utente | Documenti di Microsoft
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
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
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
ms.openlocfilehash: b1ab1501309823b1565d5198fff25edf2927a2ce
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="5db2b-102">Costanti definite dall'utente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5db2b-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="5db2b-103">Una costante è un nome significativo che prende il posto di un numero o una stringa che non cambia.</span><span class="sxs-lookup"><span data-stu-id="5db2b-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="5db2b-104">Costanti di archiviano i valori, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5db2b-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="5db2b-105">È possibile utilizzare costanti definite da controlli o ai componenti utilizzati oppure è possibile creare.</span><span class="sxs-lookup"><span data-stu-id="5db2b-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="5db2b-106">Vengono descritte le costanti personalizzate come *definita dall'utente*.</span><span class="sxs-lookup"><span data-stu-id="5db2b-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="5db2b-107">Consente di dichiarare una costante con il `Const` istruzione, utilizzando le stesse linee guida per la creazione di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="5db2b-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="5db2b-108">Se `Option Strict` è `On`, è necessario dichiarare in modo esplicito il tipo di costante.</span><span class="sxs-lookup"><span data-stu-id="5db2b-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="5db2b-109">Utilizzo dell'istruzione const</span><span class="sxs-lookup"><span data-stu-id="5db2b-109">Const Statement Usage</span></span>  
 <span data-ttu-id="5db2b-110">Oggetto `Const` istruzione può rappresentare un matematica o data/ora quantità:</span><span class="sxs-lookup"><span data-stu-id="5db2b-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 <span data-ttu-id="5db2b-111">[!code-vb[VbEnumsTask&#10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5db2b-111">[!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span></span>  
  
 <span data-ttu-id="5db2b-112">È inoltre possibile definire `String` costanti:</span><span class="sxs-lookup"><span data-stu-id="5db2b-112">It also can define `String` constants:</span></span>  
  
 <span data-ttu-id="5db2b-113">[!code-vb[13 VbEnumsTask](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5db2b-113">[!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span></span>  
  
 <span data-ttu-id="5db2b-114">L'espressione a destra del segno di uguale ( `=` ) è spesso un numero o valore letterale stringa, ma può essere anche un'espressione che restituisce un numero o stringa (anche se tale espressione non può contenere chiamate alle funzioni).</span><span class="sxs-lookup"><span data-stu-id="5db2b-114">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="5db2b-115">È anche possibile definire le costanti in termini di costanti definite in precedenza:</span><span class="sxs-lookup"><span data-stu-id="5db2b-115">You can even define constants in terms of previously defined constants:</span></span>  
  
 <span data-ttu-id="5db2b-116">[!code-vb[VbEnumsTask&#15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5db2b-116">[!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span></span>  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="5db2b-117">Ambito delle costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="5db2b-117">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="5db2b-118">Oggetto `Const` ambito dell'istruzione è uguale a quello di una variabile dichiarata nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="5db2b-118">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="5db2b-119">È possibile specificare l'ambito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5db2b-119">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="5db2b-120">Per creare una costante che esiste solo all'interno di una routine, dichiararla all'interno di tale procedura.</span><span class="sxs-lookup"><span data-stu-id="5db2b-120">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="5db2b-121">Per creare una costante che sia disponibile per tutte le routine all'interno di una classe, ma non per il codice all'esterno di tale modulo, dichiararla nella sezione dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="5db2b-121">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="5db2b-122">Per creare una costante che sia disponibile per tutti i membri di un assembly, ma non ai client all'esterno dell'assembly, dichiararla utilizzando il `Friend` (parola chiave) nella sezione dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="5db2b-122">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="5db2b-123">Per creare una costante che sia disponibile in tutta l'applicazione, dichiararla utilizzando il `Public` (parola chiave) nelle dichiarazioni di sezione della classe.</span><span class="sxs-lookup"><span data-stu-id="5db2b-123">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="5db2b-124">Per ulteriori informazioni, vedere [procedura: dichiarare una costante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="5db2b-124">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="5db2b-125">Riferimenti circolari</span><span class="sxs-lookup"><span data-stu-id="5db2b-125">Avoiding Circular References</span></span>  
 <span data-ttu-id="5db2b-126">Poiché le costanti possono essere definite in termini di altre costanti, è possibile creare inavvertitamente un *ciclo*, o un riferimento circolare, tra due o più costanti.</span><span class="sxs-lookup"><span data-stu-id="5db2b-126">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="5db2b-127">Si verifica un ciclo quando si dispone di due o più costanti pubbliche, ognuno dei quali viene definito come l'altro, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5db2b-127">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 <span data-ttu-id="5db2b-128">[!code-vb[VbEnumsTask&#16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="5db2b-128">[!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span></span>  
<span data-ttu-id="5db2b-129">[!code-vb[VbEnumsTask n.&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="5db2b-129">[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span></span>  
  
 <span data-ttu-id="5db2b-130">Se si verifica un ciclo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="5db2b-130">If a cycle occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db2b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5db2b-131">See Also</span></span>  
 <span data-ttu-id="5db2b-132">[Const (istruzione)](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-132">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="5db2b-133"> [Tipi di dati costanti e letterali](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-133"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="5db2b-134"> [Costanti ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-134"> [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span></span>  
<span data-ttu-id="5db2b-135"> [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-135"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span></span>  
<span data-ttu-id="5db2b-136"> [Cenni preliminari sulle enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-136"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="5db2b-137"> [Cenni preliminari sulle costanti](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-137"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="5db2b-138"> [Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-138"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="5db2b-139"> [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="5db2b-139"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="5db2b-140"> [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="5db2b-140"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
