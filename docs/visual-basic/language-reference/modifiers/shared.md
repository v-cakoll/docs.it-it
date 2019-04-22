---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 12c81a9a0651088a348afeaff3b71935d289da53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816283"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="9b584-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b584-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="9b584-103">Specifica che uno o più elementi di programmazione dichiarati sono associati a una classe o struttura in generale e non a una specifica istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9b584-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b584-104">Note</span><span class="sxs-lookup"><span data-stu-id="9b584-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="9b584-105">Quando usare condivisi</span><span class="sxs-lookup"><span data-stu-id="9b584-105">When to Use Shared</span></span>  
 <span data-ttu-id="9b584-106">Quando un membro di una classe o struttura rende disponibili per ogni istanza, anziché *condiviso*, in cui ogni istanza mantiene la propria copia.</span><span class="sxs-lookup"><span data-stu-id="9b584-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="9b584-107">Ciò è utile, ad esempio, se il valore di una variabile si applica all'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b584-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="9b584-108">Se si dichiara la variabile `Shared`, quindi tutte le istanze di accederanno al percorso di archiviazione stesso e, se un'istanza viene modificato il valore della variabile, tutte le istanze di accederanno il valore aggiornato.</span><span class="sxs-lookup"><span data-stu-id="9b584-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="9b584-109">La condivisione non modifica il livello di accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="9b584-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="9b584-110">Ad esempio, un membro di classe può essere condivisi e privati (accessibili solo dall'interno della classe), o non condivisa e pubblici.</span><span class="sxs-lookup"><span data-stu-id="9b584-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="9b584-111">Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9b584-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9b584-112">Regole</span><span class="sxs-lookup"><span data-stu-id="9b584-112">Rules</span></span>  
  
-   <span data-ttu-id="9b584-113">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="9b584-113">**Declaration Context.**</span></span> <span data-ttu-id="9b584-114">Si può usare `Shared` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="9b584-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="9b584-115">Ciò significa che il contesto della dichiarazione per un `Shared` elemento deve essere una classe o struttura e non può essere un file di origine, lo spazio dei nomi o procedure.</span><span class="sxs-lookup"><span data-stu-id="9b584-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="9b584-116">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="9b584-116">**Combined Modifiers.**</span></span> <span data-ttu-id="9b584-117">Non è possibile specificare `Shared` assieme [esegue l'override](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), o [ Statico](../../../visual-basic/language-reference/modifiers/static.md) nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="9b584-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="9b584-118">**Accessing.**</span><span class="sxs-lookup"><span data-stu-id="9b584-118">**Accessing.**</span></span> <span data-ttu-id="9b584-119">Accedere a un elemento condiviso, qualificarlo con il nome di classe o struttura, non con il nome della variabile di un'istanza specifica della relativa classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9b584-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="9b584-120">Anche insufficienti creare un'istanza di una classe o struttura per accedere ai relativi membri condivisi.</span><span class="sxs-lookup"><span data-stu-id="9b584-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="9b584-121">L'esempio seguente chiama la routine condivisa <xref:System.Double.IsNaN%2A> esposti dal <xref:System.Double> struttura.</span><span class="sxs-lookup"><span data-stu-id="9b584-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="9b584-122">**Condivisione implicita.**</span><span class="sxs-lookup"><span data-stu-id="9b584-122">**Implicit Sharing.**</span></span> <span data-ttu-id="9b584-123">Non è possibile usare la `Shared` modificatore in un [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md), ma le costanti vengono condivisi in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="9b584-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="9b584-124">Analogamente, non è possibile dichiarare un membro di un modulo o un'interfaccia come `Shared`, ma vengono condivisi in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="9b584-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="9b584-125">Comportamento</span><span class="sxs-lookup"><span data-stu-id="9b584-125">Behavior</span></span>  
  
-   <span data-ttu-id="9b584-126">**Spazio di archiviazione.**</span><span class="sxs-lookup"><span data-stu-id="9b584-126">**Storage.**</span></span> <span data-ttu-id="9b584-127">Una variabile condivisa o un evento viene archiviato in memoria solo una volta, indipendentemente dal numero di istanze è creare della relativa classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9b584-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="9b584-128">Analogamente, una routine condivisa o una proprietà contiene un solo set di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="9b584-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="9b584-129">**L'accesso tramite una variabile di istanza.**</span><span class="sxs-lookup"><span data-stu-id="9b584-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="9b584-130">È possibile accedere a un elemento condiviso da qualificarlo con il nome di una variabile che contiene una specifica istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9b584-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="9b584-131">Sebbene questo solitamente funziona come previsto, il compilatore genera un messaggio di avviso ed effettua l'accesso tramite il nome della classe o struttura anziché la variabile.</span><span class="sxs-lookup"><span data-stu-id="9b584-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="9b584-132">**L'accesso tramite un'espressione dell'istanza.**</span><span class="sxs-lookup"><span data-stu-id="9b584-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="9b584-133">Se si accede a un elemento condiviso tramite un'espressione che restituisce un'istanza della classe o struttura, il compilatore effettua l'accesso mediante il nome di classe o struttura anziché la valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="9b584-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="9b584-134">Ciò produce risultati imprevisti se si prevede l'espressione per eseguire altre azioni, oltre a restituire l'istanza.</span><span class="sxs-lookup"><span data-stu-id="9b584-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="9b584-135">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9b584-135">The following example illustrates this.</span></span>  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="9b584-136">Nell'esempio precedente, il compilatore genera un messaggio di avviso entrambi volte il codice accede alla variabile condivisa `total` tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9b584-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="9b584-137">In ogni caso effettua l'accesso direttamente tramite la classe `shareTotal` e non viene utilizzata alcuna istanza.</span><span class="sxs-lookup"><span data-stu-id="9b584-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="9b584-138">Nel caso della chiamata alla routine `returnClass`, questo significa che non genera anche una chiamata a `returnClass`, pertanto non viene eseguita l'azione aggiuntiva di visualizzazione "Funzione returnClass () denominato".</span><span class="sxs-lookup"><span data-stu-id="9b584-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="9b584-139">Il modificatore `Shared` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b584-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9b584-140">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="9b584-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="9b584-141">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="9b584-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="9b584-142">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="9b584-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="9b584-143">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="9b584-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="9b584-144">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="9b584-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="9b584-145">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="9b584-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b584-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b584-146">See also</span></span>

- [<span data-ttu-id="9b584-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="9b584-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="9b584-148">Static</span><span class="sxs-lookup"><span data-stu-id="9b584-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="9b584-149">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b584-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="9b584-150">Routine</span><span class="sxs-lookup"><span data-stu-id="9b584-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="9b584-151">Strutture</span><span class="sxs-lookup"><span data-stu-id="9b584-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="9b584-152">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="9b584-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
