---
title: 'Procedura: dichiarare una struttura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650027"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="e7f64-102">Procedura: dichiarare una struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7f64-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="e7f64-103">Iniziare con una dichiarazione di struttura di [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), e terminano con il `End` `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e7f64-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End` `Structure` statement.</span></span> <span data-ttu-id="e7f64-104">Tra queste due istruzioni è necessario dichiarare almeno un *elemento*.</span><span class="sxs-lookup"><span data-stu-id="e7f64-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="e7f64-105">Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento e non condiviso.</span><span class="sxs-lookup"><span data-stu-id="e7f64-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="e7f64-106">Non è possibile inizializzare uno degli elementi di struttura nella dichiarazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="e7f64-107">Quando si dichiara una variabile per un tipo di struttura, è possibile accedervi tramite la variabile per assegnare valori agli elementi.</span><span class="sxs-lookup"><span data-stu-id="e7f64-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="e7f64-108">Per una descrizione delle differenze tra classi e strutture, vedere [strutture e classi](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="e7f64-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="e7f64-109">A scopo dimostrativo, si consideri una situazione in cui si desidera tenere traccia di nome, numero di telefono e stipendio del dipendente.</span><span class="sxs-lookup"><span data-stu-id="e7f64-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="e7f64-110">Una struttura consente di eseguire questa operazione in una singola variabile.</span><span class="sxs-lookup"><span data-stu-id="e7f64-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="e7f64-111">Per dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="e7f64-111">To declare a structure</span></span>  
  
1.  <span data-ttu-id="e7f64-112">Creare l'inizio e fine delle istruzioni per la struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="e7f64-113">È possibile specificare il livello di accesso di una struttura utilizzando il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privata](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), oppure è possibile attenderne Per impostazione predefinita `Public`.</span><span class="sxs-lookup"><span data-stu-id="e7f64-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  <span data-ttu-id="e7f64-114">Aggiungere elementi al corpo della struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="e7f64-115">Una struttura deve contenere almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="e7f64-115">A structure must have at least one element.</span></span> <span data-ttu-id="e7f64-116">È necessario dichiarare ogni elemento e specificare un livello di accesso per questo file.</span><span class="sxs-lookup"><span data-stu-id="e7f64-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="e7f64-117">Se si utilizza il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md) senza alcuna parola chiave, l'accessibilità per impostazione predefinita `Public`.</span><span class="sxs-lookup"><span data-stu-id="e7f64-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="e7f64-118">Il `salary` campo nell'esempio precedente è `Private`, vale a dire che non è accessibile dall'esterno della struttura, anche da una classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e7f64-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="e7f64-119">Tuttavia, il `giveRaise` procedura `Public`, pertanto può essere chiamata dall'esterno della struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="e7f64-120">Analogamente, è possibile generare il `salaryReviewTime` evento dall'esterno della struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="e7f64-121">Oltre alle variabili, `Sub` procedure e gli eventi, è inoltre possibile definire le costanti, `Function` procedure e le proprietà in una struttura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="e7f64-122">È possibile definire al massimo una proprietà come il *proprietà predefinita*, se è necessario almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="e7f64-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="e7f64-123">È possibile gestire un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedura.</span><span class="sxs-lookup"><span data-stu-id="e7f64-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="e7f64-124">Per ulteriori informazioni, vedere [procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="e7f64-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f64-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7f64-125">See Also</span></span>  
 [<span data-ttu-id="e7f64-126">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e7f64-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e7f64-127">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="e7f64-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="e7f64-128">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="e7f64-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="e7f64-129">Tipi valore e tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="e7f64-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e7f64-130">Strutture</span><span class="sxs-lookup"><span data-stu-id="e7f64-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="e7f64-131">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e7f64-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="e7f64-132">Variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="e7f64-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [<span data-ttu-id="e7f64-133">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="e7f64-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="e7f64-134">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="e7f64-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="e7f64-135">Tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="e7f64-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
