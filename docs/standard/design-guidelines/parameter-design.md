---
title: Progettazione di parametri
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 78eb07503810e75d14bcd73740fe429e2f73475e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743672"
---
# <a name="parameter-design"></a><span data-ttu-id="942d5-102">Progettazione di parametri</span><span class="sxs-lookup"><span data-stu-id="942d5-102">Parameter design</span></span>

<span data-ttu-id="942d5-103">In questa sezione vengono fornite linee guida generali sulla progettazione dei parametri, incluse le sezioni con linee guida per il controllo degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="942d5-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="942d5-104">Inoltre, è necessario fare riferimento alle linee guida descritte in [denominazione dei parametri](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="942d5-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>

 <span data-ttu-id="942d5-105">✔️ utilizzare il tipo di parametro meno derivato che fornisce la funzionalità richiesta dal membro.</span><span class="sxs-lookup"><span data-stu-id="942d5-105">✔️ DO use the least derived parameter type that provides the functionality required by the member.</span></span>

 <span data-ttu-id="942d5-106">Si supponga, ad esempio, di voler progettare un metodo che enumera una raccolta e stampa ogni elemento nella console.</span><span class="sxs-lookup"><span data-stu-id="942d5-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="942d5-107">Questo metodo deve prendere <xref:System.Collections.IEnumerable> come parametro, non <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="942d5-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>

 <span data-ttu-id="942d5-108">❌ non utilizzano parametri riservati.</span><span class="sxs-lookup"><span data-stu-id="942d5-108">❌ DO NOT use reserved parameters.</span></span>

 <span data-ttu-id="942d5-109">Se in una versione futura è necessario più input per un membro, è possibile aggiungere un nuovo overload.</span><span class="sxs-lookup"><span data-stu-id="942d5-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>

 <span data-ttu-id="942d5-110">❌ non dispongono di metodi esposti pubblicamente che accettano puntatori, matrici di puntatori o matrici multidimensionali come parametri.</span><span class="sxs-lookup"><span data-stu-id="942d5-110">❌ DO NOT have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>

 <span data-ttu-id="942d5-111">I puntatori e le matrici multidimensionali sono relativamente difficili da utilizzare correttamente.</span><span class="sxs-lookup"><span data-stu-id="942d5-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="942d5-112">In quasi tutti i casi, le API possono essere riprogettate per evitare di assumere questi tipi come parametri.</span><span class="sxs-lookup"><span data-stu-id="942d5-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>

 <span data-ttu-id="942d5-113">✔️ inserire tutti i parametri di `out` dopo tutti i parametri per valore e `ref` (escluse le matrici di parametri), anche se si verifica un'incoerenza nell'ordinamento dei parametri tra gli overload (vedere [Overload dei membri](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="942d5-113">✔️ DO place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>

 <span data-ttu-id="942d5-114">I parametri di `out` possono essere considerati come valori restituiti aggiuntivi e la loro raggruppamento rende la firma del metodo più semplice da comprendere.</span><span class="sxs-lookup"><span data-stu-id="942d5-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>

 <span data-ttu-id="942d5-115">✔️ essere coerenti nei parametri di denominazione quando si esegue l'override dei membri o si implementano membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="942d5-115">✔️ DO be consistent in naming parameters when overriding members or implementing interface members.</span></span>

 <span data-ttu-id="942d5-116">Ciò comunicherà meglio la relazione tra i metodi.</span><span class="sxs-lookup"><span data-stu-id="942d5-116">This better communicates the relationship between the methods.</span></span>

### <a name="choose-between-enum-and-boolean-parameters"></a><span data-ttu-id="942d5-117">Scegliere tra i parametri enum e Boolean</span><span class="sxs-lookup"><span data-stu-id="942d5-117">Choose between enum and boolean parameters</span></span>
 <span data-ttu-id="942d5-118">✔️ utilizzare enum se un membro avrebbe altrimenti due o più parametri booleani.</span><span class="sxs-lookup"><span data-stu-id="942d5-118">✔️ DO use enums if a member would otherwise have two or more Boolean parameters.</span></span>

 <span data-ttu-id="942d5-119">❌ non utilizzano valori booleani, a meno che non si sia certi che non sarà mai necessario più di due valori.</span><span class="sxs-lookup"><span data-stu-id="942d5-119">❌ DO NOT use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>

 <span data-ttu-id="942d5-120">Le enumerazioni forniscono una certa spazio per l'aggiunta futura di valori, ma è necessario tenere presenti tutte le implicazioni dell'aggiunta di valori alle enumerazioni, descritte in [enum design](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="942d5-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>

 <span data-ttu-id="942d5-121">✔️ CONSIDERARE l'utilizzo di valori booleani per i parametri del costruttore che sono veri e propri a due Stati e vengono semplicemente utilizzati per inizializzare le proprietà booleane.</span><span class="sxs-lookup"><span data-stu-id="942d5-121">✔️ CONSIDER using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>

### <a name="validate-arguments"></a><span data-ttu-id="942d5-122">Convalida argomenti</span><span class="sxs-lookup"><span data-stu-id="942d5-122">Validate arguments</span></span>
 <span data-ttu-id="942d5-123">✔️ convalidare gli argomenti passati a membri pubblici, protetti o implementati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="942d5-123">✔️ DO validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="942d5-124">Genera <xref:System.ArgumentException?displayProperty=nameWithType>o una delle relative sottoclassi se la convalida ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="942d5-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>

 <span data-ttu-id="942d5-125">Si noti che la convalida effettiva non deve necessariamente essere eseguita nel membro pubblico o protetto.</span><span class="sxs-lookup"><span data-stu-id="942d5-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="942d5-126">Potrebbe verificarsi a un livello inferiore in una routine privata o interna.</span><span class="sxs-lookup"><span data-stu-id="942d5-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="942d5-127">Il punto principale è che l'intera superficie esposta agli utenti finali controlla gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="942d5-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>

 <span data-ttu-id="942d5-128">✔️ generano <xref:System.ArgumentNullException> se viene passato un argomento null e il membro non supporta gli argomenti null.</span><span class="sxs-lookup"><span data-stu-id="942d5-128">✔️ DO throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>

 <span data-ttu-id="942d5-129">✔️ convalidare i parametri enum.</span><span class="sxs-lookup"><span data-stu-id="942d5-129">✔️ DO validate enum parameters.</span></span>

 <span data-ttu-id="942d5-130">Non presupporre che gli argomenti enum siano compresi nell'intervallo definito dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="942d5-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="942d5-131">CLR consente il cast di qualsiasi valore intero in un valore enum anche se il valore non è definito nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="942d5-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>

 <span data-ttu-id="942d5-132">❌ non utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per i controlli dell'intervallo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="942d5-132">❌ DO NOT use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>

 <span data-ttu-id="942d5-133">✔️ tenere presente che gli argomenti modificabili potrebbero essere stati modificati dopo che sono stati convalidati.</span><span class="sxs-lookup"><span data-stu-id="942d5-133">✔️ DO be aware that mutable arguments might have changed after they were validated.</span></span>

 <span data-ttu-id="942d5-134">Se il membro è sensibile alla sicurezza, è consigliabile creare una copia e quindi convalidare ed elaborare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="942d5-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>

### <a name="pass-parameters"></a><span data-ttu-id="942d5-135">Parametri pass</span><span class="sxs-lookup"><span data-stu-id="942d5-135">Pass parameters</span></span>
 <span data-ttu-id="942d5-136">Dal punto di vista di una finestra di progettazione del Framework, sono disponibili tre gruppi principali di parametri: parametri per valore, parametri di `ref` e parametri di `out`.</span><span class="sxs-lookup"><span data-stu-id="942d5-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>

 <span data-ttu-id="942d5-137">Quando un argomento viene passato tramite un parametro per valore, il membro riceve una copia dell'argomento effettivo passato.</span><span class="sxs-lookup"><span data-stu-id="942d5-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="942d5-138">Se l'argomento è un tipo valore, viene inserita una copia dell'argomento nello stack.</span><span class="sxs-lookup"><span data-stu-id="942d5-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="942d5-139">Se l'argomento è un tipo di riferimento, viene inserita una copia del riferimento nello stack.</span><span class="sxs-lookup"><span data-stu-id="942d5-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="942d5-140">I linguaggi CLR più diffusi, ad C#esempio Visual Basic e C++, per impostazione predefinita passano i parametri per valore.</span><span class="sxs-lookup"><span data-stu-id="942d5-140">Most popular CLR languages, such as C#, Visual Basic, and C++, default to passing parameters by value.</span></span>

 <span data-ttu-id="942d5-141">Quando un argomento viene passato tramite un parametro di `ref`, il membro riceve un riferimento all'argomento effettivo passato.</span><span class="sxs-lookup"><span data-stu-id="942d5-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="942d5-142">Se l'argomento è un tipo valore, viene inserito un riferimento all'argomento nello stack.</span><span class="sxs-lookup"><span data-stu-id="942d5-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="942d5-143">Se l'argomento è un tipo di riferimento, nello stack viene inserito un riferimento al riferimento.</span><span class="sxs-lookup"><span data-stu-id="942d5-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="942d5-144">è possibile utilizzare i parametri `Ref` per consentire al membro di modificare gli argomenti passati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="942d5-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>

 <span data-ttu-id="942d5-145">`Out` parametri sono simili ai parametri `ref`, con alcune piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="942d5-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="942d5-146">Il parametro viene inizialmente considerato non assegnato e non può essere letto nel corpo del membro prima che venga assegnato un valore.</span><span class="sxs-lookup"><span data-stu-id="942d5-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="942d5-147">Inoltre, è necessario assegnare un valore al parametro prima che il membro restituisca.</span><span class="sxs-lookup"><span data-stu-id="942d5-147">Also, the parameter has to be assigned some value before the member returns.</span></span>

 <span data-ttu-id="942d5-148">❌ evitare di utilizzare parametri `out` o `ref`.</span><span class="sxs-lookup"><span data-stu-id="942d5-148">❌ AVOID using `out` or `ref` parameters.</span></span>

 <span data-ttu-id="942d5-149">Per usare i parametri `out` o `ref` è necessaria un'esperienza con i puntatori, informazioni sulla differenza tra tipi di valore e tipi di riferimento e metodi di gestione con più valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="942d5-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="942d5-150">Inoltre, la differenza tra `out` e i parametri di `ref` non è ampiamente riconosciuta.</span><span class="sxs-lookup"><span data-stu-id="942d5-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="942d5-151">Gli architetti di Framework che progettano i destinatari generali non dovrebbero aspettarsi che gli utenti lavorino con `out` o `ref` parametri.</span><span class="sxs-lookup"><span data-stu-id="942d5-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>

 <span data-ttu-id="942d5-152">❌ non passano i tipi riferimento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="942d5-152">❌ DO NOT pass reference types by reference.</span></span>

 <span data-ttu-id="942d5-153">Esistono alcune eccezioni limitate alla regola, ad esempio un metodo che può essere usato per scambiare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="942d5-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>

### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="942d5-154">Membri con numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="942d5-154">Members with variable number of parameters</span></span>
 <span data-ttu-id="942d5-155">I membri che possono assumere un numero variabile di argomenti vengono espressi fornendo un parametro di matrice.</span><span class="sxs-lookup"><span data-stu-id="942d5-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="942d5-156">Ad esempio, <xref:System.String> fornisce il metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="942d5-156">For example, <xref:System.String> provides the following method:</span></span>

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 <span data-ttu-id="942d5-157">Un utente può quindi chiamare il metodo <xref:System.String.Format%2A?displayProperty=nameWithType>, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="942d5-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 <span data-ttu-id="942d5-158">Se si C# aggiunge la parola chiave params a un parametro di matrice, il parametro viene modificato in un parametro di matrice denominato params e viene fornito un collegamento per la creazione di una matrice temporanea.</span><span class="sxs-lookup"><span data-stu-id="942d5-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 <span data-ttu-id="942d5-159">Questa operazione consente all'utente di chiamare il metodo passando gli elementi della matrice direttamente nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="942d5-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>

 `String.Format("File {0} not found in {1}",filename,directory);`

 <span data-ttu-id="942d5-160">Si noti che la parola chiave params può essere aggiunta solo all'ultimo parametro nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="942d5-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>

 <span data-ttu-id="942d5-161">✔️ CONSIGLIABILE aggiungere la parola chiave params ai parametri di matrice se si prevede che gli utenti finali passino matrici con un numero ridotto di elementi.</span><span class="sxs-lookup"><span data-stu-id="942d5-161">✔️ CONSIDER adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="942d5-162">Se si prevede che molti elementi vengano passati negli scenari comuni, gli utenti probabilmente non passano questi elementi inline, quindi la parola chiave params non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="942d5-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>

 <span data-ttu-id="942d5-163">❌ evitare di utilizzare matrici params se il chiamante avrebbe quasi sempre l'input già presente in una matrice.</span><span class="sxs-lookup"><span data-stu-id="942d5-163">❌ AVOID using params arrays if the caller would almost always have the input already in an array.</span></span>

 <span data-ttu-id="942d5-164">I membri con parametri di matrice di byte, ad esempio, non vengono mai chiamati passando singoli byte.</span><span class="sxs-lookup"><span data-stu-id="942d5-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="942d5-165">Per questo motivo, i parametri della matrice di byte nel .NET Framework non usano la parola chiave params.</span><span class="sxs-lookup"><span data-stu-id="942d5-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>

 <span data-ttu-id="942d5-166">❌ non utilizzano matrici params se la matrice viene modificata dal membro che accetta il parametro di matrice params.</span><span class="sxs-lookup"><span data-stu-id="942d5-166">❌ DO NOT use params arrays if the array is modified by the member taking the params array parameter.</span></span>

 <span data-ttu-id="942d5-167">Poiché molti compilatori trasformano gli argomenti nel membro in una matrice temporanea nel sito di chiamata, la matrice potrebbe essere un oggetto temporaneo e pertanto le modifiche apportate alla matrice andranno perse.</span><span class="sxs-lookup"><span data-stu-id="942d5-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>

 <span data-ttu-id="942d5-168">✔️ CONSIGLIABILE utilizzare la parola chiave params in un overload semplice, anche se un sovraccarico più complesso non lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="942d5-168">✔️ CONSIDER using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>

 <span data-ttu-id="942d5-169">Chiedere se gli utenti hanno valore con la matrice params in un overload anche se non era in tutti gli overload.</span><span class="sxs-lookup"><span data-stu-id="942d5-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>

 <span data-ttu-id="942d5-170">✔️ provare a ordinare i parametri per consentire l'uso della parola chiave params.</span><span class="sxs-lookup"><span data-stu-id="942d5-170">✔️ DO try to order parameters to make it possible to use the params keyword.</span></span>

 <span data-ttu-id="942d5-171">✔️ CONSIGLIABILE fornire overload speciali e percorsi di codice per le chiamate con un numero ridotto di argomenti in API estremamente sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="942d5-171">✔️ CONSIDER providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>

 <span data-ttu-id="942d5-172">In questo modo è possibile evitare la creazione di oggetti Array quando l'API viene chiamata con un numero ridotto di argomenti.</span><span class="sxs-lookup"><span data-stu-id="942d5-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="942d5-173">Formare i nomi dei parametri prendendo una forma singolare del parametro di matrice e aggiungendo un suffisso numerico.</span><span class="sxs-lookup"><span data-stu-id="942d5-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>

 <span data-ttu-id="942d5-174">Questa operazione deve essere eseguita solo se si intende usare in modo speciale l'intero percorso del codice, non solo creare una matrice e chiamare il metodo più generale.</span><span class="sxs-lookup"><span data-stu-id="942d5-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>

 <span data-ttu-id="942d5-175">✔️ tenere presente che null può essere passato come argomento di matrice params.</span><span class="sxs-lookup"><span data-stu-id="942d5-175">✔️ DO be aware that null could be passed as a params array argument.</span></span>

 <span data-ttu-id="942d5-176">Prima di eseguire l'elaborazione, è necessario verificare che la matrice non sia null.</span><span class="sxs-lookup"><span data-stu-id="942d5-176">You should validate that the array is not null before processing.</span></span>

 <span data-ttu-id="942d5-177">❌ non utilizzano i metodi di `varargs`, altrimenti noti come puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="942d5-177">❌ DO NOT use the `varargs` methods, otherwise known as the ellipsis.</span></span>

 <span data-ttu-id="942d5-178">Alcuni linguaggi CLR, ad esempio C++, supportano una convenzione alternativa per passare elenchi di parametri variabili denominati `varargs` metodi.</span><span class="sxs-lookup"><span data-stu-id="942d5-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="942d5-179">La convenzione non deve essere utilizzata nei Framework, perché non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="942d5-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>

### <a name="pointer-parameters"></a><span data-ttu-id="942d5-180">Parametri del puntatore</span><span class="sxs-lookup"><span data-stu-id="942d5-180">Pointer parameters</span></span>
 <span data-ttu-id="942d5-181">In generale, i puntatori non devono essere visualizzati nella superficie pubblica di un Framework di codice gestito ben progettato.</span><span class="sxs-lookup"><span data-stu-id="942d5-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="942d5-182">Nella maggior parte dei casi, i puntatori devono essere incapsulati.</span><span class="sxs-lookup"><span data-stu-id="942d5-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="942d5-183">In alcuni casi, tuttavia, i puntatori sono necessari per motivi di interoperabilità e l'utilizzo di puntatori in tali casi è appropriato.</span><span class="sxs-lookup"><span data-stu-id="942d5-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>

 <span data-ttu-id="942d5-184">✔️ forniscono un'alternativa per qualsiasi membro che accetta un argomento puntatore, perché i puntatori non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="942d5-184">✔️ DO provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>

 <span data-ttu-id="942d5-185">❌ evitare il controllo degli argomenti costosi degli argomenti del puntatore.</span><span class="sxs-lookup"><span data-stu-id="942d5-185">❌ AVOID doing expensive argument checking of pointer arguments.</span></span>

 <span data-ttu-id="942d5-186">per la progettazione di membri con puntatori, ✔️ seguire convenzioni comuni relative al puntatore.</span><span class="sxs-lookup"><span data-stu-id="942d5-186">✔️ DO follow common pointer-related conventions when designing members with pointers.</span></span>

 <span data-ttu-id="942d5-187">Ad esempio, non è necessario passare l'indice iniziale, perché per ottenere lo stesso risultato è possibile utilizzare l'aritmetica semplice del puntatore.</span><span class="sxs-lookup"><span data-stu-id="942d5-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>

 <span data-ttu-id="942d5-188">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="942d5-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="942d5-189">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="942d5-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="942d5-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="942d5-190">See also</span></span>

- [<span data-ttu-id="942d5-191">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="942d5-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="942d5-192">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="942d5-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
