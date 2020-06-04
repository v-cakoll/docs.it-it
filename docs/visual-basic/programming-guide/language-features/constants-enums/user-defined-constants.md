---
title: Costanti definite dall'utente
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 14f3de39eb8d8e6820e2b40792a8e8e57217e410
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414376"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="d558e-102">Costanti definite dall'utente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d558e-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="d558e-103">Una costante è un nome significativo che prende il posto di un numero o di una stringa che non cambia.</span><span class="sxs-lookup"><span data-stu-id="d558e-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="d558e-104">Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d558e-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="d558e-105">È possibile usare le costanti definite dai controlli o dai componenti usati oppure è possibile crearne di personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d558e-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="d558e-106">Le costanti create dall'utente vengono descritte come *definite dall'utente*.</span><span class="sxs-lookup"><span data-stu-id="d558e-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="d558e-107">Viene dichiarata una costante con l' `Const` istruzione, usando le stesse linee guida per la creazione di un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="d558e-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="d558e-108">Se `Option Strict` è `On` , è necessario dichiarare in modo esplicito il tipo di costante.</span><span class="sxs-lookup"><span data-stu-id="d558e-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="d558e-109">Utilizzo istruzioni Const</span><span class="sxs-lookup"><span data-stu-id="d558e-109">Const Statement Usage</span></span>  
 <span data-ttu-id="d558e-110">Un' `Const` istruzione può rappresentare una quantità matematica o di data/ora:</span><span class="sxs-lookup"><span data-stu-id="d558e-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 <span data-ttu-id="d558e-111">Consente inoltre di definire `String` costanti:</span><span class="sxs-lookup"><span data-stu-id="d558e-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 <span data-ttu-id="d558e-112">L'espressione a destra del segno di uguale ( `=` ) è spesso un numero o una stringa letterale, ma può anche essere un'espressione che restituisce un numero o una stringa (anche se tale espressione non può contenere chiamate alle funzioni).</span><span class="sxs-lookup"><span data-stu-id="d558e-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="d558e-113">È anche possibile definire costanti in termini di costanti definite in precedenza:</span><span class="sxs-lookup"><span data-stu-id="d558e-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="d558e-114">Ambito delle costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="d558e-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="d558e-115">`Const`L'ambito di un'istruzione è identico a quello di una variabile dichiarata nella stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="d558e-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="d558e-116">È possibile specificare l'ambito in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d558e-116">You can specify scope in any of the following ways:</span></span>  
  
- <span data-ttu-id="d558e-117">Per creare una costante che esiste solo all'interno di una routine, dichiararla all'interno di tale procedura.</span><span class="sxs-lookup"><span data-stu-id="d558e-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
- <span data-ttu-id="d558e-118">Per creare una costante disponibile per tutte le routine all'interno di una classe, ma non per il codice esterno a tale modulo, dichiararla nella sezione delle dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="d558e-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="d558e-119">Per creare una costante disponibile a tutti i membri di un assembly, ma non all'esterno dei client dell'assembly, dichiararla usando la `Friend` parola chiave nella sezione delle dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="d558e-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
- <span data-ttu-id="d558e-120">Per creare una costante disponibile nell'applicazione, dichiararla usando la `Public` parola chiave nella sezione delle dichiarazioni della classe.</span><span class="sxs-lookup"><span data-stu-id="d558e-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="d558e-121">Per altre informazioni, vedere [procedura: dichiarare una costante](how-to-declare-a-constant.md).</span><span class="sxs-lookup"><span data-stu-id="d558e-121">For more information, see [How to: Declare A Constant](how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="d558e-122">Evitare riferimenti circolari</span><span class="sxs-lookup"><span data-stu-id="d558e-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="d558e-123">Poiché le costanti possono essere definite in termini di altre costanti, è possibile creare inavvertitamente un *ciclo*o un riferimento circolare tra due o più costanti.</span><span class="sxs-lookup"><span data-stu-id="d558e-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="d558e-124">Si verifica un ciclo quando si hanno due o più costanti pubbliche, ciascuna delle quali è definita in base all'altra, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d558e-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 <span data-ttu-id="d558e-125">Se si verifica un ciclo, Visual Basic genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d558e-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d558e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d558e-126">See also</span></span>

- [<span data-ttu-id="d558e-127">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="d558e-127">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
- [<span data-ttu-id="d558e-128">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="d558e-128">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="d558e-129">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="d558e-129">Constants and Enumerations</span></span>](index.md)
- [<span data-ttu-id="d558e-130">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="d558e-130">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="d558e-131">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="d558e-131">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="d558e-132">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="d558e-132">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="d558e-133">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="d558e-133">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="d558e-134">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="d558e-134">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="d558e-135">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="d558e-135">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
