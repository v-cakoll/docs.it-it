---
title: 'Procedura: Dichiarare una struttura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bfed5c969466cb427e6c94d39bfcc6a6e007c320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672045"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="7178f-102">Procedura: Dichiarare una struttura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7178f-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="7178f-103">Iniziare una dichiarazione structure con la [istruzione Structure](../../../../visual-basic/language-reference/statements/structure-statement.md), e terminano con la `End` `Structure` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7178f-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End` `Structure` statement.</span></span> <span data-ttu-id="7178f-104">Tra le due istruzioni seguenti è necessario dichiarare almeno *elemento*.</span><span class="sxs-lookup"><span data-stu-id="7178f-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="7178f-105">Gli elementi possono essere di qualsiasi tipo di dati, ma almeno uno deve essere una variabile non condivisa o un evento e non condiviso.</span><span class="sxs-lookup"><span data-stu-id="7178f-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="7178f-106">Non è possibile inizializzare uno degli elementi struttura nella dichiarazione di struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="7178f-107">Quando si dichiara una variabile di un tipo di struttura, è possibile accedervi tramite la variabile per assegnare valori agli elementi.</span><span class="sxs-lookup"><span data-stu-id="7178f-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="7178f-108">Per una descrizione delle differenze tra classi e strutture, vedere [classi e strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="7178f-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="7178f-109">A scopo dimostrativo, si consideri una situazione in cui si vuole tenere traccia di nome, numero di telefono e stipendio del dipendente.</span><span class="sxs-lookup"><span data-stu-id="7178f-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="7178f-110">Una struttura consente di eseguire questa operazione in una singola variabile.</span><span class="sxs-lookup"><span data-stu-id="7178f-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="7178f-111">Per dichiarare una struttura</span><span class="sxs-lookup"><span data-stu-id="7178f-111">To declare a structure</span></span>  
  
1.  <span data-ttu-id="7178f-112">Creazione di inizio e fine delle istruzioni per la struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="7178f-113">È possibile specificare il livello di accesso di una struttura con il [pubbliche](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privato](../../../../visual-basic/language-reference/modifiers/private.md) (parola chiave), oppure è possibile lasciare che Per impostazione predefinita `Public`.</span><span class="sxs-lookup"><span data-stu-id="7178f-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  <span data-ttu-id="7178f-114">Aggiungere elementi al corpo della struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="7178f-115">Una struttura deve avere almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="7178f-115">A structure must have at least one element.</span></span> <span data-ttu-id="7178f-116">È necessario dichiarare ogni elemento e specificare un livello di accesso per esso.</span><span class="sxs-lookup"><span data-stu-id="7178f-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="7178f-117">Se si usa la [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) senza alcuna parola chiave, per impostazione predefinita l'accessibilità `Public`.</span><span class="sxs-lookup"><span data-stu-id="7178f-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
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
  
     <span data-ttu-id="7178f-118">Il `salary` campo nell'esempio precedente è `Private`, vale a dire che è accessibile dall'esterno della struttura, anche dalla classe che contiene.</span><span class="sxs-lookup"><span data-stu-id="7178f-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="7178f-119">Tuttavia, il `giveRaise` routine `Public`, pertanto può essere chiamato dall'esterno della struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="7178f-120">Analogamente, è possibile generare il `salaryReviewTime` evento dall'esterno della struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="7178f-121">Oltre alle variabili, `Sub` routine ed eventi, è anche possibile definire le costanti, `Function` procedure e le proprietà in una struttura.</span><span class="sxs-lookup"><span data-stu-id="7178f-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="7178f-122">È possibile definire al massimo una proprietà come il *predefiniti delle proprietà*, a condizione che richiede almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="7178f-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="7178f-123">È possibile gestire un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedure.</span><span class="sxs-lookup"><span data-stu-id="7178f-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="7178f-124">Per altre informazioni, vedere [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="7178f-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7178f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7178f-125">See also</span></span>
- [<span data-ttu-id="7178f-126">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7178f-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7178f-127">Tipi di dati elementari</span><span class="sxs-lookup"><span data-stu-id="7178f-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="7178f-128">Tipi di dati compositi</span><span class="sxs-lookup"><span data-stu-id="7178f-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="7178f-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="7178f-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="7178f-130">Strutture</span><span class="sxs-lookup"><span data-stu-id="7178f-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="7178f-131">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7178f-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="7178f-132">Variabili di struttura</span><span class="sxs-lookup"><span data-stu-id="7178f-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="7178f-133">Strutture e altri elementi di programmazione</span><span class="sxs-lookup"><span data-stu-id="7178f-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="7178f-134">Strutture e classi</span><span class="sxs-lookup"><span data-stu-id="7178f-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="7178f-135">Tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="7178f-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
