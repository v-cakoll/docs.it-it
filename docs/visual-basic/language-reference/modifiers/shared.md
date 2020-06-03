---
title: Shared
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
ms.openlocfilehash: 000cc13bc6e80914e9a21b6ee60e91127809ee08
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307085"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="0c0bb-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c0bb-102">Shared (Visual Basic)</span></span>

<span data-ttu-id="0c0bb-103">Specifica che uno o più elementi di programmazione dichiarati sono associati a una classe o a una struttura di grandi dimensioni e non a un'istanza specifica della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>

## <a name="when-to-use-shared"></a><span data-ttu-id="0c0bb-104">Quando usare Shared</span><span class="sxs-lookup"><span data-stu-id="0c0bb-104">When to Use Shared</span></span>

<span data-ttu-id="0c0bb-105">La condivisione di un membro di una classe o di una struttura lo rende disponibile per ogni istanza, anziché *non condivisa*, in cui ogni istanza mantiene la propria copia.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-105">Sharing a member of a class or structure makes it available to every instance, rather than *non-shared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="0c0bb-106">Questa operazione è utile, ad esempio, se il valore di una variabile viene applicato all'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-106">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="0c0bb-107">Se si dichiara tale variabile come `Shared` , tutte le istanze accedono allo stesso percorso di archiviazione e se un'istanza modifica il valore della variabile, tutte le istanze accedono al valore aggiornato.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-107">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>

<span data-ttu-id="0c0bb-108">La condivisione non modifica il livello di accesso di un membro.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-108">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="0c0bb-109">Un membro di una classe, ad esempio, può essere condiviso e privato (accessibile solo dall'interno della classe) o non condiviso e pubblico.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-109">For example, a class member can be shared and private (accessible only from within the class), or non-shared and public.</span></span> <span data-ttu-id="0c0bb-110">Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0c0bb-110">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

## <a name="rules"></a><span data-ttu-id="0c0bb-111">Regole</span><span class="sxs-lookup"><span data-stu-id="0c0bb-111">Rules</span></span>

- <span data-ttu-id="0c0bb-112">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="0c0bb-112">**Declaration Context.**</span></span> <span data-ttu-id="0c0bb-113">Si può usare `Shared` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-113">You can use `Shared` only at module level.</span></span> <span data-ttu-id="0c0bb-114">Ciò significa che il contesto di dichiarazione per un `Shared` elemento deve essere una classe o una struttura e non può essere un file di origine, uno spazio dei nomi o una procedura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-114">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>

- <span data-ttu-id="0c0bb-115">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-115">**Combined Modifiers.**</span></span> <span data-ttu-id="0c0bb-116">Non è possibile specificare `Shared` insieme a [override](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)o [static](../../../visual-basic/language-reference/modifiers/static.md) nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-116">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>

- <span data-ttu-id="0c0bb-117">**Accesso.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-117">**Accessing.**</span></span> <span data-ttu-id="0c0bb-118">Per accedere a un elemento condiviso, è necessario qualificarlo con il nome della classe o della struttura, non con il nome della variabile di un'istanza specifica della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-118">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="0c0bb-119">Non è nemmeno necessario creare un'istanza di una classe o di una struttura per accedere ai relativi membri condivisi.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-119">You do not even have to create an instance of a class or structure to access its shared members.</span></span>

     <span data-ttu-id="0c0bb-120">Nell'esempio seguente viene chiamata la procedura condivisa <xref:System.Double.IsNaN%2A> esposta dalla <xref:System.Double> struttura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-120">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- <span data-ttu-id="0c0bb-121">**Condivisione implicita.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-121">**Implicit Sharing.**</span></span> <span data-ttu-id="0c0bb-122">Non è possibile usare il `Shared` modificatore in un' [istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md), ma le costanti sono implicitamente condivise.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-122">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="0c0bb-123">Analogamente, non è possibile dichiarare un membro di un modulo o un'interfaccia come `Shared` , ma sono implicitamente condivisi.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-123">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>

## <a name="behavior"></a><span data-ttu-id="0c0bb-124">Comportamento</span><span class="sxs-lookup"><span data-stu-id="0c0bb-124">Behavior</span></span>

- <span data-ttu-id="0c0bb-125">**Archiviazione.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-125">**Storage.**</span></span> <span data-ttu-id="0c0bb-126">Una variabile o un evento condiviso viene archiviato in memoria una sola volta, indipendentemente dal numero di istanze create dalla classe o dalla struttura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-126">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="0c0bb-127">Analogamente, una routine o una proprietà condivisa include un solo set di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-127">Similarly, a shared procedure or property holds only one set of local variables.</span></span>

- <span data-ttu-id="0c0bb-128">**Accesso tramite una variabile di istanza.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-128">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="0c0bb-129">È possibile accedere a un elemento condiviso qualificando il nome di una variabile che contiene un'istanza specifica della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-129">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="0c0bb-130">Sebbene questo in genere funzioni come previsto, il compilatore genera un messaggio di avviso e rende l'accesso tramite la classe o il nome della struttura anziché la variabile.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-130">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>

- <span data-ttu-id="0c0bb-131">**Accesso tramite un'espressione di istanza.**</span><span class="sxs-lookup"><span data-stu-id="0c0bb-131">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="0c0bb-132">Se si accede a un elemento condiviso tramite un'espressione che restituisce un'istanza della relativa classe o struttura, il compilatore consente di accedere tramite il nome della classe o della struttura anziché di valutare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-132">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="0c0bb-133">Ciò produce risultati imprevisti se si desidera che l'espressione esegua altre azioni e restituisca l'istanza.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-133">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="0c0bb-134">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-134">The following example illustrates this.</span></span>
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     <span data-ttu-id="0c0bb-135">Nell'esempio precedente, il compilatore genera un messaggio di avviso entrambe le volte che il codice accede alla proprietà condivisa `Total` tramite un'istanza.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-135">In the preceding example, the compiler generates a warning message both times the code accesses the shared property `Total` through an instance.</span></span> <span data-ttu-id="0c0bb-136">In ogni caso rende l'accesso direttamente tramite la classe `ShareTotal` e non usa alcuna istanza.</span><span class="sxs-lookup"><span data-stu-id="0c0bb-136">In each case it makes the access directly through the class `ShareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="0c0bb-137">Nel caso della chiamata prevista alla procedura `ReturnClass` , ciò significa che non viene anche generata una chiamata a `ReturnClass` , quindi non viene eseguita l'azione aggiuntiva di visualizzazione della funzione "ReturnClass () chiamata".</span><span class="sxs-lookup"><span data-stu-id="0c0bb-137">In the case of the intended call to the procedure `ReturnClass`, this means it does not even generate a call to `ReturnClass`, so the additional action of displaying "Function ReturnClass() called" is not performed.</span></span>

<span data-ttu-id="0c0bb-138">Il modificatore `Shared` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c0bb-138">The `Shared` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="0c0bb-139">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="0c0bb-139">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="0c0bb-140">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="0c0bb-140">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="0c0bb-141">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="0c0bb-141">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="0c0bb-142">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0c0bb-142">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="0c0bb-143">Property Statement</span><span class="sxs-lookup"><span data-stu-id="0c0bb-143">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="0c0bb-144">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="0c0bb-144">Sub Statement</span></span>](../statements/sub-statement.md)
  
## <a name="see-also"></a><span data-ttu-id="0c0bb-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c0bb-145">See also</span></span>

- [<span data-ttu-id="0c0bb-146">Shadows</span><span class="sxs-lookup"><span data-stu-id="0c0bb-146">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="0c0bb-147">Statico</span><span class="sxs-lookup"><span data-stu-id="0c0bb-147">Static</span></span>](static.md)
- [<span data-ttu-id="0c0bb-148">Durata in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c0bb-148">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="0c0bb-149">Procedure</span><span class="sxs-lookup"><span data-stu-id="0c0bb-149">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="0c0bb-150">Strutture</span><span class="sxs-lookup"><span data-stu-id="0c0bb-150">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0c0bb-151">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="0c0bb-151">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
