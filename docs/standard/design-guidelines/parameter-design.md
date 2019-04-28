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
author: KrzysztofCwalina
ms.openlocfilehash: 5a0f6e0fab5d0f2fe8574e348fc6b8ae726eeb99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757404"
---
# <a name="parameter-design"></a><span data-ttu-id="446fa-102">Progettazione di parametri</span><span class="sxs-lookup"><span data-stu-id="446fa-102">Parameter Design</span></span>
<span data-ttu-id="446fa-103">Questa sezione vengono fornite linee guida generali sulla progettazione di parametro, incluse le sezioni con le linee guida per la verifica di argomenti.</span><span class="sxs-lookup"><span data-stu-id="446fa-103">This section provides broad guidelines on parameter design, including sections with guidelines for checking arguments.</span></span> <span data-ttu-id="446fa-104">Inoltre, è consigliabile consultare le linee guida descritte nel [parametri di denominazione](../../../docs/standard/design-guidelines/naming-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="446fa-104">In addition, you should refer to the guidelines described in [Naming Parameters](../../../docs/standard/design-guidelines/naming-parameters.md).</span></span>  
  
 <span data-ttu-id="446fa-105">**✓ DO** utilizzare il tipo di parametro meno derivato che fornisce le funzionalità richieste da un membro.</span><span class="sxs-lookup"><span data-stu-id="446fa-105">**✓ DO** use the least derived parameter type that provides the functionality required by the member.</span></span>  
  
 <span data-ttu-id="446fa-106">Si supponga, ad esempio, che si vuole progettare un metodo che enumera una raccolta e la stampa di ogni elemento nella console.</span><span class="sxs-lookup"><span data-stu-id="446fa-106">For example, suppose you want to design a method that enumerates a collection and prints each item to the console.</span></span> <span data-ttu-id="446fa-107">Tale metodo richiederà <xref:System.Collections.IEnumerable> come parametro, non <xref:System.Collections.ArrayList> o <xref:System.Collections.IList>, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="446fa-107">Such a method should take <xref:System.Collections.IEnumerable> as the parameter, not <xref:System.Collections.ArrayList> or <xref:System.Collections.IList>, for example.</span></span>  
  
 <span data-ttu-id="446fa-108">**X DO NOT** utilizzare parametri riservati.</span><span class="sxs-lookup"><span data-stu-id="446fa-108">**X DO NOT** use reserved parameters.</span></span>  
  
 <span data-ttu-id="446fa-109">Se sono necessarie più input per un membro nelle versioni future, è possibile aggiungere un nuovo overload.</span><span class="sxs-lookup"><span data-stu-id="446fa-109">If more input to a member is needed in some future version, a new overload can be added.</span></span>  
  
 <span data-ttu-id="446fa-110">**X DO NOT** sono esposte pubblicamente i metodi che accettano puntatori, matrici di puntatori o le matrici multidimensionali come parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-110">**X DO NOT** have publicly exposed methods that take pointers, arrays of pointers, or multidimensional arrays as parameters.</span></span>  
  
 <span data-ttu-id="446fa-111">I puntatori e matrici multidimensionali sono relativamente difficili da utilizzare in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="446fa-111">Pointers and multidimensional arrays are relatively difficult to use properly.</span></span> <span data-ttu-id="446fa-112">Nella quasi totalità dei casi, le API possono essere riprogettate per evitare di creare questi tipi come parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-112">In almost all cases, APIs can be redesigned to avoid taking these types as parameters.</span></span>  
  
 <span data-ttu-id="446fa-113">**✓ DO** inserire tutti `out` parametri che seguono tutti il base al valore e `ref` parametri (esclusi matrici di parametro), anche se il risultato è un'incoerenza nel parametro ordinamento viene eseguito tra gli overload (vedere [membro L'overload](../../../docs/standard/design-guidelines/member-overloading.md)).</span><span class="sxs-lookup"><span data-stu-id="446fa-113">**✓ DO** place all `out` parameters following all of the by-value and `ref` parameters (excluding parameter arrays), even if it results in an inconsistency in parameter ordering between overloads (see [Member Overloading](../../../docs/standard/design-guidelines/member-overloading.md)).</span></span>  
  
 <span data-ttu-id="446fa-114">Il `out` parametri possono essere considerati come valori di ritorno a capo e raggruppandoli rende la firma del metodo più facile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="446fa-114">The `out` parameters can be seen as extra return values, and grouping them together makes the method signature easier to understand.</span></span>  
  
 <span data-ttu-id="446fa-115">**✓ DO** sia sempre coerente denominazione dei parametri quando si esegue l'override di membri o di implementazione di membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="446fa-115">**✓ DO** be consistent in naming parameters when overriding members or implementing interface members.</span></span>  
  
 <span data-ttu-id="446fa-116">Ciò comunica meglio la relazione tra i metodi.</span><span class="sxs-lookup"><span data-stu-id="446fa-116">This better communicates the relationship between the methods.</span></span>  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a><span data-ttu-id="446fa-117">Scelta tra l'enumerazione e i parametri booleani</span><span class="sxs-lookup"><span data-stu-id="446fa-117">Choosing Between Enum and Boolean Parameters</span></span>  
 <span data-ttu-id="446fa-118">**✓ DO** utilizzare enumerazioni se un membro in caso contrario sarebbe due o più parametri booleani.</span><span class="sxs-lookup"><span data-stu-id="446fa-118">**✓ DO** use enums if a member would otherwise have two or more Boolean parameters.</span></span>  
  
 <span data-ttu-id="446fa-119">**X DO NOT** utilizzare valori booleani, a meno che non si è assolutamente certi non sarà mai necessario per più di due valori.</span><span class="sxs-lookup"><span data-stu-id="446fa-119">**X DO NOT** use Booleans unless you are absolutely sure there will never be a need for more than two values.</span></span>  
  
 <span data-ttu-id="446fa-120">Le enumerazioni offrono un margine di future addizione dei valori, ma è necessario essere consapevoli di tutte le implicazioni dell'aggiunta di valori alle enumerazioni senza ambito, descritte nelle [progettazione di Enum](../../../docs/standard/design-guidelines/enum.md).</span><span class="sxs-lookup"><span data-stu-id="446fa-120">Enums give you some room for future addition of values, but you should be aware of all the implications of adding values to enums, which are described in [Enum Design](../../../docs/standard/design-guidelines/enum.md).</span></span>  
  
 <span data-ttu-id="446fa-121">**✓ CONSIDER** utilizzando valori booleani per i parametri del costruttore che sono realmente due stati, valori e vengono utilizzati per inizializzare le proprietà booleane.</span><span class="sxs-lookup"><span data-stu-id="446fa-121">**✓ CONSIDER** using Booleans for constructor parameters that are truly two-state values and are simply used to initialize Boolean properties.</span></span>  
  
### <a name="validating-arguments"></a><span data-ttu-id="446fa-122">Convalida di argomenti</span><span class="sxs-lookup"><span data-stu-id="446fa-122">Validating Arguments</span></span>  
 <span data-ttu-id="446fa-123">**✓ DO** convalidare gli argomenti passati ai membri pubblici, protetti o implementati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="446fa-123">**✓ DO** validate arguments passed to public, protected, or explicitly implemented members.</span></span> <span data-ttu-id="446fa-124">Generare <xref:System.ArgumentException?displayProperty=nameWithType>, o una delle sue sottoclassi, se la convalida non riesce.</span><span class="sxs-lookup"><span data-stu-id="446fa-124">Throw <xref:System.ArgumentException?displayProperty=nameWithType>, or one of its subclasses, if the validation fails.</span></span>  
  
 <span data-ttu-id="446fa-125">Si noti che la convalida effettiva non deve necessariamente essere eseguita nel membro pubblico o protetto se stesso.</span><span class="sxs-lookup"><span data-stu-id="446fa-125">Note that the actual validation does not necessarily have to happen in the public or protected member itself.</span></span> <span data-ttu-id="446fa-126">Questo può verificarsi a un livello inferiore in alcune routine privato o interno.</span><span class="sxs-lookup"><span data-stu-id="446fa-126">It could happen at a lower level in some private or internal routine.</span></span> <span data-ttu-id="446fa-127">Il punto principale è che l'intera area di superficie esposta agli utenti finali controlla gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="446fa-127">The main point is that the entire surface area that is exposed to the end users checks the arguments.</span></span>  
  
 <span data-ttu-id="446fa-128">**✓ DO** throw <xref:System.ArgumentNullException> se viene passato un argomento null e il membro non supporta argomenti null.</span><span class="sxs-lookup"><span data-stu-id="446fa-128">**✓ DO** throw <xref:System.ArgumentNullException> if a null argument is passed and the member does not support null arguments.</span></span>  
  
 <span data-ttu-id="446fa-129">**✓ DO** convalidare i parametri enum.</span><span class="sxs-lookup"><span data-stu-id="446fa-129">**✓ DO** validate enum parameters.</span></span>  
  
 <span data-ttu-id="446fa-130">Non presupporre enum argomenti sarà compreso nell'intervallo definito dal tipo enum.</span><span class="sxs-lookup"><span data-stu-id="446fa-130">Do not assume enum arguments will be in the range defined by the enum.</span></span> <span data-ttu-id="446fa-131">CLR consente di eseguire il cast di qualsiasi valore intero in un valore enum, anche se il valore non è definito nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="446fa-131">The CLR allows casting any integer value into an enum value even if the value is not defined in the enum.</span></span>  
  
 <span data-ttu-id="446fa-132">**X DO NOT** utilizzare <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> per intervallo di enumerazione controlla.</span><span class="sxs-lookup"><span data-stu-id="446fa-132">**X DO NOT** use <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> for enum range checks.</span></span>  
  
 <span data-ttu-id="446fa-133">**✓ DO** tenere presente che gli argomenti modificabili sia stato modificato dopo che sono stati convalidati.</span><span class="sxs-lookup"><span data-stu-id="446fa-133">**✓ DO** be aware that mutable arguments might have changed after they were validated.</span></span>  
  
 <span data-ttu-id="446fa-134">Se il membro è relative alla sicurezza, vengono fornite informazioni utili per creare una copia e quindi convalidare ed elaborare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="446fa-134">If the member is security sensitive, you are encouraged to make a copy and then validate and process the argument.</span></span>  
  
### <a name="parameter-passing"></a><span data-ttu-id="446fa-135">Passaggio dei parametri</span><span class="sxs-lookup"><span data-stu-id="446fa-135">Parameter Passing</span></span>  
 <span data-ttu-id="446fa-136">Dalla prospettiva di una finestra di progettazione di framework, sono disponibili tre gruppi principali di parametri: parametri, dal valore `ref` parametri, e `out` parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-136">From the perspective of a framework designer, there are three main groups of parameters: by-value parameters, `ref` parameters, and `out` parameters.</span></span>  
  
 <span data-ttu-id="446fa-137">Quando viene passato un argomento tramite un parametro in base al valore, il membro riceve una copia dell'argomento effettivo passato.</span><span class="sxs-lookup"><span data-stu-id="446fa-137">When an argument is passed through a by-value parameter, the member receives a copy of the actual argument passed in.</span></span> <span data-ttu-id="446fa-138">Se l'argomento è un tipo di valore, una copia dell'argomento viene inserita nello stack.</span><span class="sxs-lookup"><span data-stu-id="446fa-138">If the argument is a value type, a copy of the argument is put on the stack.</span></span> <span data-ttu-id="446fa-139">Se l'argomento è un tipo riferimento, una copia del riferimento viene inserita nello stack.</span><span class="sxs-lookup"><span data-stu-id="446fa-139">If the argument is a reference type, a copy of the reference is put on the stack.</span></span> <span data-ttu-id="446fa-140">Linguaggi di Common Language Runtime più diffusi, ad esempio c#, VB.NET e C++, predefinito per il passaggio di parametri per valore.</span><span class="sxs-lookup"><span data-stu-id="446fa-140">Most popular CLR languages, such as C#, VB.NET, and C++, default to passing parameters by value.</span></span>  
  
 <span data-ttu-id="446fa-141">Quando viene passato un argomento tramite un `ref` parametro, il membro riceve un riferimento all'argomento effettivo passato.</span><span class="sxs-lookup"><span data-stu-id="446fa-141">When an argument is passed through a `ref` parameter, the member receives a reference to the actual argument passed in.</span></span> <span data-ttu-id="446fa-142">Se l'argomento è un tipo di valore, viene inserito un riferimento all'argomento nello stack.</span><span class="sxs-lookup"><span data-stu-id="446fa-142">If the argument is a value type, a reference to the argument is put on the stack.</span></span> <span data-ttu-id="446fa-143">Se l'argomento è un tipo riferimento, viene inserito un riferimento al riferimento nello stack.</span><span class="sxs-lookup"><span data-stu-id="446fa-143">If the argument is a reference type, a reference to the reference is put on the stack.</span></span> <span data-ttu-id="446fa-144">`Ref` i parametri utilizzabile per consentire il membro modificare gli argomenti passati dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="446fa-144">`Ref` parameters can be used to allow the member to modify arguments passed by the caller.</span></span>  
  
 <span data-ttu-id="446fa-145">`Out` i parametri sono simili a `ref` parametri, con alcune piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="446fa-145">`Out` parameters are similar to `ref` parameters, with some small differences.</span></span> <span data-ttu-id="446fa-146">Il parametro verrà considerato inizialmente non assegnati e non possono essere letti nel corpo del membro prima che venga assegnata a un valore.</span><span class="sxs-lookup"><span data-stu-id="446fa-146">The parameter is initially considered unassigned and cannot be read in the member body before it is assigned some value.</span></span> <span data-ttu-id="446fa-147">Inoltre, il parametro deve essere assegnato un valore prima che venga restituito il membro.</span><span class="sxs-lookup"><span data-stu-id="446fa-147">Also, the parameter has to be assigned some value before the member returns.</span></span>  
  
 <span data-ttu-id="446fa-148">**X AVOID** mediante `out` o `ref` parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-148">**X AVOID** using `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="446fa-149">Usando `out` o `ref` parametri richiede esperienza nell'utilizzo dei puntatori, informazioni sulle differiscano tra i tipi di valore e tipi di riferimento e gestione dei metodi con più valori restituiti.</span><span class="sxs-lookup"><span data-stu-id="446fa-149">Using `out` or `ref` parameters requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values.</span></span> <span data-ttu-id="446fa-150">Inoltre, la differenza tra `out` e `ref` parametri non è stato ampiamente riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="446fa-150">Also, the difference between `out` and `ref` parameters is not widely understood.</span></span> <span data-ttu-id="446fa-151">Gli architetti di Framework progettazione per un pubblico generico non possono prevedere agli utenti di utilizzare i `out` o `ref` parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-151">Framework architects designing for a general audience should not expect users to master working with `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="446fa-152">**X DO NOT** passare i tipi di riferimento per riferimento.</span><span class="sxs-lookup"><span data-stu-id="446fa-152">**X DO NOT** pass reference types by reference.</span></span>  
  
 <span data-ttu-id="446fa-153">Esistono alcune eccezioni alla regola, ad esempio un metodo che può essere utilizzato per scambiare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="446fa-153">There are some limited exceptions to the rule, such as a method that can be used to swap references.</span></span>  
  
### <a name="members-with-variable-number-of-parameters"></a><span data-ttu-id="446fa-154">Membri con un numero variabile di parametri</span><span class="sxs-lookup"><span data-stu-id="446fa-154">Members with Variable Number of Parameters</span></span>  
 <span data-ttu-id="446fa-155">I membri che possono accettare un numero variabile di argomenti sono espressi fornendo un parametro di matrice.</span><span class="sxs-lookup"><span data-stu-id="446fa-155">Members that can take a variable number of arguments are expressed by providing an array parameter.</span></span> <span data-ttu-id="446fa-156">Ad esempio, <xref:System.String> fornisce il metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="446fa-156">For example, <xref:System.String> provides the following method:</span></span>  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 <span data-ttu-id="446fa-157">Un utente può quindi chiamare il <xref:System.String.Format%2A?displayProperty=nameWithType> (metodo), come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="446fa-157">A user can then call the <xref:System.String.Format%2A?displayProperty=nameWithType> method, as follows:</span></span>  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 <span data-ttu-id="446fa-158">Aggiunta la parola chiave params c# a un parametro di matrice viene modificato il parametro a un parametro di matrice cosiddette params e fornisce un collegamento per la creazione di una matrice temporanea.</span><span class="sxs-lookup"><span data-stu-id="446fa-158">Adding the C# params keyword to an array parameter changes the parameter to a so-called params array parameter and provides a shortcut to creating a temporary array.</span></span>  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 <span data-ttu-id="446fa-159">In questo modo consente all'utente di chiamare il metodo passando gli elementi della matrice direttamente nell'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="446fa-159">Doing this allows the user to call the method by passing the array elements directly in the argument list.</span></span>  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 <span data-ttu-id="446fa-160">Si noti che è possibile aggiungere la parola chiave params solo all'ultimo parametro nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-160">Note that the params keyword can be added only to the last parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="446fa-161">**✓ CONSIDER** aggiungendo la parola chiave params ai parametri di matrice, se si prevede che gli utenti finali per passare matrici con un numero limitato di elementi.</span><span class="sxs-lookup"><span data-stu-id="446fa-161">**✓ CONSIDER** adding the params keyword to array parameters if you expect the end users to pass arrays with a small number of elements.</span></span> <span data-ttu-id="446fa-162">Se si prevede che un numero elevato di elementi verrà passato in comune scenari, gli utenti probabilmente non supera tali elementi inline comunque e pertanto non è necessaria la parola chiave params.</span><span class="sxs-lookup"><span data-stu-id="446fa-162">If it’s expected that lots of elements will be passed in common scenarios, users will probably not pass these elements inline anyway, and so the params keyword is not necessary.</span></span>  
  
 <span data-ttu-id="446fa-163">**X AVOID** utilizzo delle matrici di parametri se il chiamante quasi sempre necessario l'input già in una matrice.</span><span class="sxs-lookup"><span data-stu-id="446fa-163">**X AVOID** using params arrays if the caller would almost always have the input already in an array.</span></span>  
  
 <span data-ttu-id="446fa-164">Ad esempio, i membri con i parametri di matrice di byte non verrebbero quasi mai essere chiamati passando byte singoli.</span><span class="sxs-lookup"><span data-stu-id="446fa-164">For example, members with byte array parameters would almost never be called by passing individual bytes.</span></span> <span data-ttu-id="446fa-165">Per questo motivo, i parametri di matrice di byte in .NET Framework non usano la parola chiave params.</span><span class="sxs-lookup"><span data-stu-id="446fa-165">For this reason, byte array parameters in the .NET Framework do not use the params keyword.</span></span>  
  
 <span data-ttu-id="446fa-166">**X DO NOT** utilizzare matrici params se la matrice viene modificata dal membro che accetta il parametro di matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-166">**X DO NOT** use params arrays if the array is modified by the member taking the params array parameter.</span></span>  
  
 <span data-ttu-id="446fa-167">A causa del fatto che molti compilatori trasformare gli argomenti per il membro in una matrice temporanea nel sito di chiamata, la matrice potrebbe essere un oggetto temporaneo e pertanto alcuna modifica alla matrice andranno perse.</span><span class="sxs-lookup"><span data-stu-id="446fa-167">Because of the fact that many compilers turn the arguments to the member into a temporary array at the call site, the array might be a temporary object, and therefore any modifications to the array will be lost.</span></span>  
  
 <span data-ttu-id="446fa-168">**✓ CONSIDER** utilizzando la parola chiave params in un overload semplice, anche se un overload più complesso non è stato possibile utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="446fa-168">**✓ CONSIDER** using the params keyword in a simple overload, even if a more complex overload could not use it.</span></span>  
  
 <span data-ttu-id="446fa-169">Chiedersi se gli utenti sarebbero valore la presenza di una matrice di parametri in uno degli overload anche se non è stato in tutti gli overload.</span><span class="sxs-lookup"><span data-stu-id="446fa-169">Ask yourself if users would value having the params array in one overload even if it wasn’t in all overloads.</span></span>  
  
 <span data-ttu-id="446fa-170">**✓ DO** tenta di ordinare i parametri per consentono di utilizzare la parola chiave params.</span><span class="sxs-lookup"><span data-stu-id="446fa-170">**✓ DO** try to order parameters to make it possible to use the params keyword.</span></span>  
  
 <span data-ttu-id="446fa-171">**✓ CONSIDER** fornendo overload speciali e i percorsi del codice per le chiamate con un numero ridotto di argomenti nelle API molto sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="446fa-171">**✓ CONSIDER** providing special overloads and code paths for calls with a small number of arguments in extremely performance-sensitive APIs.</span></span>  
  
 <span data-ttu-id="446fa-172">Questo rende possibile per evitare di creare gli oggetti matrice quando viene chiamata l'API con un numero ridotto di argomenti.</span><span class="sxs-lookup"><span data-stu-id="446fa-172">This makes it possible to avoid creating array objects when the API is called with a small number of arguments.</span></span> <span data-ttu-id="446fa-173">Costituiscono i nomi dei parametri prendendo una forma singolare del parametro della matrice e aggiunta di un suffisso numerico.</span><span class="sxs-lookup"><span data-stu-id="446fa-173">Form the names of the parameters by taking a singular form of the array parameter and adding a numeric suffix.</span></span>  
  
 <span data-ttu-id="446fa-174">È consigliabile farlo solo se si intende specialistico il percorso di codice completo, non è sufficiente creare una matrice e chiamare il metodo più generico.</span><span class="sxs-lookup"><span data-stu-id="446fa-174">You should only do this if you are going to special-case the entire code path, not just create an array and call the more general method.</span></span>  
  
 <span data-ttu-id="446fa-175">**✓ DO** tenere presente che null è stato passato come argomento di matrice di parametri.</span><span class="sxs-lookup"><span data-stu-id="446fa-175">**✓ DO** be aware that null could be passed as a params array argument.</span></span>  
  
 <span data-ttu-id="446fa-176">È necessario convalidare che la matrice non è null prima dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="446fa-176">You should validate that the array is not null before processing.</span></span>  
  
 <span data-ttu-id="446fa-177">**X DO NOT** usare il `varargs` metodi, altrimenti noti come i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="446fa-177">**X DO NOT** use the `varargs` methods, otherwise known as the ellipsis.</span></span>  
  
 <span data-ttu-id="446fa-178">Alcuni linguaggi CLR, ad esempio C++, supportano una convenzione alternativa per il passaggio di elenchi di parametri variabile denominati `varargs` metodi.</span><span class="sxs-lookup"><span data-stu-id="446fa-178">Some CLR languages, such as C++, support an alternative convention for passing variable parameter lists called `varargs` methods.</span></span> <span data-ttu-id="446fa-179">La convenzione non deve essere utilizzata nei Framework, perché non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="446fa-179">The convention should not be used in frameworks, because it is not CLS compliant.</span></span>  
  
### <a name="pointer-parameters"></a><span data-ttu-id="446fa-180">Parametri dei puntatori</span><span class="sxs-lookup"><span data-stu-id="446fa-180">Pointer Parameters</span></span>  
 <span data-ttu-id="446fa-181">In generale, i puntatori non devono essere visualizzati nell'area di superficie di un framework progettato correttamente il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="446fa-181">In general, pointers should not appear in the public surface area of a well-designed managed code framework.</span></span> <span data-ttu-id="446fa-182">La maggior parte dei casi, i puntatori devono essere incapsulati.</span><span class="sxs-lookup"><span data-stu-id="446fa-182">Most of the time, pointers should be encapsulated.</span></span> <span data-ttu-id="446fa-183">Tuttavia, in alcuni casi sono necessari per motivi di interoperabilità tra i puntatori e l'uso di puntatori in questi casi è appropriato.</span><span class="sxs-lookup"><span data-stu-id="446fa-183">However, in some cases pointers are required for interoperability reasons, and using pointers in such cases is appropriate.</span></span>  
  
 <span data-ttu-id="446fa-184">**✓ DO** forniscono un'alternativa per i membri che accetta un argomento di puntatore, poiché i puntatori non sono conformi a CLS.</span><span class="sxs-lookup"><span data-stu-id="446fa-184">**✓ DO** provide an alternative for any member that takes a pointer argument, because pointers are not CLS-compliant.</span></span>  
  
 <span data-ttu-id="446fa-185">**X AVOID** in questo argomento costoso il controllo degli argomenti del puntatore.</span><span class="sxs-lookup"><span data-stu-id="446fa-185">**X AVOID** doing expensive argument checking of pointer arguments.</span></span>  
  
 <span data-ttu-id="446fa-186">**✓ DO** convenzioni comuni correlati puntatore quando si progettano i membri con puntatori.</span><span class="sxs-lookup"><span data-stu-id="446fa-186">**✓ DO** follow common pointer-related conventions when designing members with pointers.</span></span>  
  
 <span data-ttu-id="446fa-187">Ad esempio, non è necessario passare l'indice di inizio, perché l'aritmetica dei puntatori semplice può essere utilizzata per ottenere lo stesso risultato.</span><span class="sxs-lookup"><span data-stu-id="446fa-187">For example, there is no need to pass the start index, because simple pointer arithmetic can be used to accomplish the same result.</span></span>  
  
 <span data-ttu-id="446fa-188">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="446fa-188">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="446fa-189">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="446fa-189">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446fa-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="446fa-190">See also</span></span>

- [<span data-ttu-id="446fa-191">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="446fa-191">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="446fa-192">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="446fa-192">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
