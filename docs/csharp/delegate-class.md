---
title: System.Delegate e la parola chiave `delegate`
description: Informazioni sulle classi di .NET che supportano i delegati e sul modo in cui vengono mappati alla parola chiave ' Delegate '.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 3cfc9925be0f191dc3fc93c02f4a8f9a40b71895
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450921"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="717d6-103">System.Delegate e la parola chiave `delegate`</span><span class="sxs-lookup"><span data-stu-id="717d6-103">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="717d6-104">Precedente</span><span class="sxs-lookup"><span data-stu-id="717d6-104">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="717d6-105">In questo articolo vengono illustrate le classi di .NET che supportano i delegati e il modo in cui vengono mappati alla parola chiave `delegate`.</span><span class="sxs-lookup"><span data-stu-id="717d6-105">This article covers the classes in .NET that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="define-delegate-types"></a><span data-ttu-id="717d6-106">Definire i tipi di delegati</span><span class="sxs-lookup"><span data-stu-id="717d6-106">Define delegate types</span></span>

<span data-ttu-id="717d6-107">Iniziamo con la parola chiave "delegate" che è essenzialmente quello che si userà per lavorare con i delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-107">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="717d6-108">Il codice che il compilatore genera quando si usa la parola chiave `delegate` eseguirà il mapping alle chiamate ai metodi che richiamano i membri delle classi <xref:System.Delegate> e <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="717d6-108">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the <xref:System.Delegate> and <xref:System.MulticastDelegate> classes.</span></span> 

<span data-ttu-id="717d6-109">Per definire un tipo delegato si usa una sintassi simile alla definizione di una firma di metodo.</span><span class="sxs-lookup"><span data-stu-id="717d6-109">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="717d6-110">È sufficiente aggiungere la parola chiave `delegate` alla definizione.</span><span class="sxs-lookup"><span data-stu-id="717d6-110">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="717d6-111">Si continuerà a usare il metodo List.Sort() come esempio.</span><span class="sxs-lookup"><span data-stu-id="717d6-111">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="717d6-112">Il primo passaggio consiste nel creare un tipo per il delegato di confronto:</span><span class="sxs-lookup"><span data-stu-id="717d6-112">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="717d6-113">Il compilatore genera una classe, derivata da `System.Delegate` che corrisponde alla firma usata (in questo caso, un metodo che restituisce un valore integer e ha due argomenti).</span><span class="sxs-lookup"><span data-stu-id="717d6-113">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="717d6-114">Il tipo di quel delegato è `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="717d6-114">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="717d6-115">Il tipo delegato `Comparison` è un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="717d6-115">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="717d6-116">Per informazioni dettagliate sui generics, vedere [qui](programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="717d6-116">For details on generics see [here](programming-guide/generics/index.md).</span></span>

<span data-ttu-id="717d6-117">Si noti che può sembrare che la sintassi dichiari una variabile, ma in effetti viene dichiarato un *tipo*.</span><span class="sxs-lookup"><span data-stu-id="717d6-117">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="717d6-118">È possibile definire tipi delegato all'interno di classi, direttamente all'interno di spazi dei nomi o anche nello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="717d6-118">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="717d6-119">La dichiarazione di tipi delegato (o altri tipi) direttamente nello spazio dei nomi globale non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="717d6-119">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span> 

<span data-ttu-id="717d6-120">Il compilatore genera anche gestori di aggiunta e rimozione per questo nuovo tipo in modo che i client di questa classe siano in grado di aggiungere e rimuovere metodi dall'elenco delle chiamate di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="717d6-120">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="717d6-121">Il compilatore impone che la firma del metodo aggiunto o rimosso corrisponda alla firma usata per la dichiarazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="717d6-121">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span> 

## <a name="declare-instances-of-delegates"></a><span data-ttu-id="717d6-122">Dichiarare istanze di delegati</span><span class="sxs-lookup"><span data-stu-id="717d6-122">Declare instances of delegates</span></span>

<span data-ttu-id="717d6-123">Dopo aver definito il delegato è possibile creare un'istanza di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="717d6-123">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="717d6-124">Come per tutte le variabili in C#, non è possibile dichiarare le istanze di delegato direttamente in uno spazio dei nomi o nello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="717d6-124">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="717d6-125">Il tipo della variabile è `Comparison<T>`, il tipo delegato definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="717d6-125">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="717d6-126">Il nome della variabile è `comparator`.</span><span class="sxs-lookup"><span data-stu-id="717d6-126">The name of the variable is `comparator`.</span></span>
 
 <span data-ttu-id="717d6-127">Il frammento di codice riportato sopra dichiara una variabile membro all'interno di una classe.</span><span class="sxs-lookup"><span data-stu-id="717d6-127">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="717d6-128">È anche possibile dichiarare variabili delegato che sono variabili locali o argomenti per i metodi.</span><span class="sxs-lookup"><span data-stu-id="717d6-128">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoke-delegates"></a><span data-ttu-id="717d6-129">Richiama delegati</span><span class="sxs-lookup"><span data-stu-id="717d6-129">Invoke delegates</span></span>

<span data-ttu-id="717d6-130">Per richiamare i metodi inclusi nell'elenco chiamate di un delegato, chiamare quel delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-130">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="717d6-131">All'interno del metodo `Sort()` il codice chiamerà il metodo di confronto per determinare l'ordine in cui inserire gli oggetti:</span><span class="sxs-lookup"><span data-stu-id="717d6-131">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="717d6-132">Nella riga precedente il codice *richiama* il metodo associato al delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-132">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="717d6-133">La variabile viene trattata come nome di metodo e per richiamarla viene usata usando la sintassi di chiamata di metodo normale.</span><span class="sxs-lookup"><span data-stu-id="717d6-133">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="717d6-134">Quella riga di codice presuppone che non esista alcuna garanzia che una destinazione sia stata aggiunta al delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-134">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="717d6-135">Se non sono state associate destinazioni, la riga precedente causerebbe la generazione di `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="717d6-135">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="717d6-136">Gli idiomi usati per risolvere questo problema sono più complessi rispetto a un semplice controllo null e sono trattati più avanti in questa [serie](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="717d6-136">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assign-add-and-remove-invocation-targets"></a><span data-ttu-id="717d6-137">Assegnare, aggiungere e rimuovere destinazioni di chiamata</span><span class="sxs-lookup"><span data-stu-id="717d6-137">Assign, add, and remove invocation targets</span></span>

<span data-ttu-id="717d6-138">Questo è il modo in cui viene definito un tipo delegato e in cui le istanze dei delegati vengono dichiarate e richiamate.</span><span class="sxs-lookup"><span data-stu-id="717d6-138">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="717d6-139">Gli sviluppatori che vogliono usare il metodo `List.Sort()` devono definire un metodo la cui firma corrisponda alla definizione di tipo delegato e assegnare il metodo al delegato usato dal metodo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="717d6-139">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="717d6-140">Questa assegnazione consente di aggiungere il metodo all'elenco delle chiamate dell'oggetto delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-140">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="717d6-141">Si supponga di voler ordinare un elenco di stringhe in base alla lunghezza.</span><span class="sxs-lookup"><span data-stu-id="717d6-141">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="717d6-142">La funzione di confronto potrebbe essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="717d6-142">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

<span data-ttu-id="717d6-143">Il metodo viene dichiarato come metodo privato.</span><span class="sxs-lookup"><span data-stu-id="717d6-143">The method is declared as a private method.</span></span> <span data-ttu-id="717d6-144">Va bene.</span><span class="sxs-lookup"><span data-stu-id="717d6-144">That's fine.</span></span> <span data-ttu-id="717d6-145">Può essere opportuno evitare che questo metodo sia parte dell'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="717d6-145">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="717d6-146">Può comunque essere usato come metodo di confronto se collegato a un delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-146">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="717d6-147">Il codice chiamante avrà questo metodo associato all'elenco di destinazione dell'oggetto delegato e potrà accedere usando quel delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-147">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="717d6-148">La relazione si crea passando tale metodo al metodo `List.Sort()`:</span><span class="sxs-lookup"><span data-stu-id="717d6-148">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="717d6-149">Si noti che viene usato il nome del metodo, senza parentesi.</span><span class="sxs-lookup"><span data-stu-id="717d6-149">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="717d6-150">L'uso del metodo come argomento indica al compilatore di convertire il riferimento al metodo in un riferimento che possa essere usato come destinazione della chiamata al delegato e di associare tale metodo come destinazione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="717d6-150">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="717d6-151">Si può anche procedere in modo esplicito dichiarando una variabile di tipo `Comparison<string>` ed eseguendo un'assegnazione:</span><span class="sxs-lookup"><span data-stu-id="717d6-151">You could also have been explicit by declaring a variable of type `Comparison<string>` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="717d6-152">Quando il metodo usato come destinazione di delegato è un metodo piccolo spesso si usa la sintassi dell'[espressione lambda](./programming-guide/statements-expressions-operators/lambda-expressions.md) per eseguire l'assegnazione:</span><span class="sxs-lookup"><span data-stu-id="717d6-152">In uses where the method being used as a delegate target is a small method, it's common to use [lambda expression](./programming-guide/statements-expressions-operators/lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="717d6-153">L'uso delle espressioni lambda per le destinazioni di delegato è descritto in dettaglio in una [sezione successiva](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="717d6-153">Using lambda expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="717d6-154">L'esempio Sort() di solito associa un singolo metodo di destinazione al delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-154">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="717d6-155">Tuttavia, gli oggetti delegati supportano gli elenchi delle chiamate con più metodi di destinazione associati a un oggetto delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-155">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="717d6-156">Classi Delegate e MulticastDelegate</span><span class="sxs-lookup"><span data-stu-id="717d6-156">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="717d6-157">Il supporto del linguaggio descritto in precedenza offre le funzionalità e il supporto in genere necessari quando si lavora con i delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-157">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="717d6-158">Tali funzionalità si basano su due classi di .NET Core Framework: <xref:System.Delegate> e <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="717d6-158">These features are built on two classes in the .NET Core framework: <xref:System.Delegate> and <xref:System.MulticastDelegate>.</span></span>

<span data-ttu-id="717d6-159">La classe `System.Delegate` e la relativa sottoclasse diretta, `System.MulticastDelegate`, forniscono il supporto del Framework per la creazione di delegati, la registrazione di metodi come destinazioni delegate e la chiamata di tutti i metodi registrati come destinazione del delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-159">The `System.Delegate` class and its single direct subclass, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span> 

<span data-ttu-id="717d6-160">È interessante notare che le classi `System.Delegate` e `System.MulticastDelegate` non sono tipi di delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-160">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="717d6-161">Offrono la base per tutti i tipi di delegati specifici.</span><span class="sxs-lookup"><span data-stu-id="717d6-161">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="717d6-162">Lo stesso processo di progettazione del linguaggio stabilisce che non è possibile dichiarare una classe che derivi da `Delegate` o `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="717d6-162">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="717d6-163">Le regole del linguaggio C# lo proibiscono.</span><span class="sxs-lookup"><span data-stu-id="717d6-163">The C# language rules prohibit it.</span></span>
 
<span data-ttu-id="717d6-164">Al contrario, il compilatore C# crea istanze di una classe derivata da `MulticastDelegate` quando si usa la parola chiave del linguaggio C# per dichiarare i tipi di delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-164">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="717d6-165">Questa progettazione ha le sue radici nella prima versione di C# e .NET.</span><span class="sxs-lookup"><span data-stu-id="717d6-165">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="717d6-166">Uno degli obiettivi per il team di progettazione era assicurarsi che il linguaggio applicasse l'indipendenza dai tipi nell'uso dei delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-166">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="717d6-167">Ciò significava garantire che i delegati venissero richiamati con il tipo e il numero di argomenti corretti.</span><span class="sxs-lookup"><span data-stu-id="717d6-167">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="717d6-168">E che ogni tipo restituito fosse correttamente indicato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="717d6-168">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="717d6-169">I delegati facevano parte della versione 1.0 di .NET, precedente ai generics.</span><span class="sxs-lookup"><span data-stu-id="717d6-169">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="717d6-170">Il modo migliore di applicare l'indipendenza dai tipi per il compilatore era creare le classi delegate concrete che rappresentavano la firma del metodo in uso.</span><span class="sxs-lookup"><span data-stu-id="717d6-170">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="717d6-171">Anche se non è possibile creare direttamente le classi derivate, vengono usati i metodi definiti per queste classi.</span><span class="sxs-lookup"><span data-stu-id="717d6-171">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="717d6-172">Vediamo quali sono i metodi più comuni da usare quando si lavora con i delegati.</span><span class="sxs-lookup"><span data-stu-id="717d6-172">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="717d6-173">Il primo è più importante aspetto da ricordare è che ogni delegato con cui si lavora è derivato da `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="717d6-173">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="717d6-174">Un delegato multicast significa che si possono richiamare più destinazioni di metodo quando la chiamata è effettuata attraverso un delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-174">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="717d6-175">Nella progettazione originale si è ritenuto utile distinguere i delegati in cui era possibile associare e richiamare un solo metodo di destinazione dai delegati in cui era possibile associare e richiamare più metodi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="717d6-175">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="717d6-176">Tale distinzione si è rivelata in pratica meno utile del previsto.</span><span class="sxs-lookup"><span data-stu-id="717d6-176">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="717d6-177">Le due classi differenti erano già state create e sono rimaste nel framework dalla versione pubblica iniziale.</span><span class="sxs-lookup"><span data-stu-id="717d6-177">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="717d6-178">I metodi che si usano più di frequente con i delegati sono `Invoke()` e `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="717d6-178">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="717d6-179">`Invoke()` richiamerà tutti i metodi che sono stati associati a un'istanza particolare del delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-179">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="717d6-180">Come osservato in precedenza, in genere i delegati vengono richiamati usando la sintassi di chiamata di metodo per la variabile delegato.</span><span class="sxs-lookup"><span data-stu-id="717d6-180">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="717d6-181">Come si vedrà [più avanti in questa serie](delegates-patterns.md), sono disponibili modelli che funzionano direttamente con questi metodi.</span><span class="sxs-lookup"><span data-stu-id="717d6-181">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="717d6-182">Ora che è stata esaminata la sintassi del linguaggio e le classi che supportano i delegati, esaminiamo il modo in cui vengono usati, creati e richiamati i delegati fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="717d6-182">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created, and invoked.</span></span>

[<span data-ttu-id="717d6-183">avanti</span><span class="sxs-lookup"><span data-stu-id="717d6-183">Next</span></span>](delegates-strongly-typed.md)
