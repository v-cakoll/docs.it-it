---
title: Funzioni locali - Guida per programmatori C#
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: b6924b8981af5115a474eeb6b2e5376dd1b17ff5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170235"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="b9198-102">Funzioni locali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b9198-102">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="b9198-103">A partire dalla versione 7.0, C# supporta le *funzioni locali*.</span><span class="sxs-lookup"><span data-stu-id="b9198-103">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="b9198-104">Le funzioni locali sono metodi privati di un tipo annidati in un altro membro.</span><span class="sxs-lookup"><span data-stu-id="b9198-104">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="b9198-105">Possono essere chiamate solo dal relativo membro contenitore.</span><span class="sxs-lookup"><span data-stu-id="b9198-105">They can only be called from their containing member.</span></span> <span data-ttu-id="b9198-106">Le funzioni locali, in particolare, possono essere dichiarate in e chiamate da:</span><span class="sxs-lookup"><span data-stu-id="b9198-106">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="b9198-107">Metodi, soprattutto metodi iteratori e metodi asincroni</span><span class="sxs-lookup"><span data-stu-id="b9198-107">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="b9198-108">Costruttori</span><span class="sxs-lookup"><span data-stu-id="b9198-108">Constructors</span></span>
- <span data-ttu-id="b9198-109">Funzioni di accesso alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b9198-109">Property accessors</span></span>
- <span data-ttu-id="b9198-110">Funzioni di accesso agli eventi</span><span class="sxs-lookup"><span data-stu-id="b9198-110">Event accessors</span></span>
- <span data-ttu-id="b9198-111">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="b9198-111">Anonymous methods</span></span>
- <span data-ttu-id="b9198-112">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="b9198-112">Lambda expressions</span></span>
- <span data-ttu-id="b9198-113">Finalizzatori</span><span class="sxs-lookup"><span data-stu-id="b9198-113">Finalizers</span></span>
- <span data-ttu-id="b9198-114">Altre funzioni locali</span><span class="sxs-lookup"><span data-stu-id="b9198-114">Other local functions</span></span>

<span data-ttu-id="b9198-115">Le funzioni locali, tuttavia, non possono essere dichiarate all'interno di un membro con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="b9198-115">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="b9198-116">In alcuni casi, è possibile usare un'espressione lambda per implementare le funzionalità supportate anche da una funzione locale.</span><span class="sxs-lookup"><span data-stu-id="b9198-116">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="b9198-117">Per un confronto, vedere [Confronto tra funzioni locali ed espressioni Lambda](../../local-functions-vs-lambdas.md).</span><span class="sxs-lookup"><span data-stu-id="b9198-117">For a comparison, see [Local functions compared to Lambda expressions](../../local-functions-vs-lambdas.md).</span></span>

<span data-ttu-id="b9198-118">Le funzioni locali rendono chiaro l'obiettivo del codice.</span><span class="sxs-lookup"><span data-stu-id="b9198-118">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="b9198-119">Chiunque legga il codice può vedere che il metodo non è richiamabile se non dal metodo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="b9198-119">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="b9198-120">Per i progetti in team, le funzioni locali impediscono anche a un altro sviluppatore di chiamare per errore il metodo direttamente da un altro punto della classe o dello struct.</span><span class="sxs-lookup"><span data-stu-id="b9198-120">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>

## <a name="local-function-syntax"></a><span data-ttu-id="b9198-121">Sintassi delle funzioni locali</span><span class="sxs-lookup"><span data-stu-id="b9198-121">Local function syntax</span></span>

<span data-ttu-id="b9198-122">Una funzione locale viene definita come metodo annidato all'interno di un membro contenitore.</span><span class="sxs-lookup"><span data-stu-id="b9198-122">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="b9198-123">La definizione presenta la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b9198-123">Its definition has the following syntax:</span></span>

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="b9198-124">Le funzioni locali possono usare i modificatori [async](../../language-reference/keywords/async.md) e [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b9198-124">Local functions can use the [async](../../language-reference/keywords/async.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

<span data-ttu-id="b9198-125">Tutte le variabili locali definite nel membro contenitore, inclusi i relativi parametri di metodo, sono accessibili nella funzione locale.</span><span class="sxs-lookup"><span data-stu-id="b9198-125">Note that all local variables that are defined in the containing member, including its method parameters, are accessible in the local function.</span></span>

<span data-ttu-id="b9198-126">A differenza di una definizione di metodo, una definizione di funzione locale non può includere il modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="b9198-126">Unlike a method definition, a local function definition cannot include the member access modifier.</span></span> <span data-ttu-id="b9198-127">Poiché tutte le funzioni locali sono private, l'integrazione di un modificatore di accesso come la parola chiave `private` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".</span><span class="sxs-lookup"><span data-stu-id="b9198-127">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>

> [!NOTE]
> <span data-ttu-id="b9198-128">Nelle versioni precedenti alla versione 8.0 `static` di C, le funzioni locali non possono includere il modificatore.</span><span class="sxs-lookup"><span data-stu-id="b9198-128">Prior to C# 8.0, local functions cannot include the `static` modifier.</span></span> <span data-ttu-id="b9198-129">L'integrazione della parola chiave `static` genera l'errore del compilatore CS0106: "Il modificatore 'private' non è valido per questo elemento".</span><span class="sxs-lookup"><span data-stu-id="b9198-129">Including the `static` keyword generates compiler error CS0106, "The modifier 'static' is not valid for this item."</span></span>

<span data-ttu-id="b9198-130">Non è possibile, inoltre, applicare attributi alla funzione locale o ai relativi parametri e parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="b9198-130">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span>

<span data-ttu-id="b9198-131">L'esempio seguente definisce una funzione locale denominata `AppendPathSeparator`, privata di un metodo denominato `GetText`:</span><span class="sxs-lookup"><span data-stu-id="b9198-131">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a><span data-ttu-id="b9198-132">Funzioni locali ed eccezioni</span><span class="sxs-lookup"><span data-stu-id="b9198-132">Local functions and exceptions</span></span>

<span data-ttu-id="b9198-133">Le funzioni locali offrono il vantaggio di consentire alle eccezioni di essere rilevate immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b9198-133">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="b9198-134">Nel caso degli iteratori di metodo, le eccezioni vengono rilevate solo nel momento in cui la sequenza restituita viene enumerata e non quando viene recuperato l'iteratore.</span><span class="sxs-lookup"><span data-stu-id="b9198-134">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="b9198-135">Nel caso dei metodi asincroni, qualsiasi eccezione generata viene rilevata mentre è attesa l'attività restituita.</span><span class="sxs-lookup"><span data-stu-id="b9198-135">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span>

<span data-ttu-id="b9198-136">L'esempio seguente definisce un metodo `OddSequence` che enumera i numeri dispari in un intervallo specifico.</span><span class="sxs-lookup"><span data-stu-id="b9198-136">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="b9198-137">Poiché al metodo enumeratore `OddSequence` viene trasmesso un numero maggiore di 100, il metodo genera una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="b9198-137">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="b9198-138">Come illustrato dall'output dell'esempio, l'eccezione viene rilevata solo nel momento in cui vengono iterati i numeri e non quando si recupera l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b9198-138">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

<span data-ttu-id="b9198-139">È possibile tuttavia generare un'eccezione mentre si esegue la convalida e prima di recuperare l'iteratore restituendo l'iteratore da una funzione locale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b9198-139">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="b9198-140">Le funzioni locali possono essere usate in modo analogo anche per gestire eccezioni esterne all'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="b9198-140">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="b9198-141">In genere, le eccezioni generate in un metodo asincrono richiedono che vengano esaminate le eccezioni interne di una <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b9198-141">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="b9198-142">Le funzioni locali consentono al codice di adottare un approccio "fail fast" e alle eccezioni di essere generate e osservate in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="b9198-142">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="b9198-143">Nell'esempio seguente viene usato un metodo asincrono denominato `GetMultipleAsync` per sospendere l'operazione per un determinato numero di secondi e restituire un valore che sia un multiplo casuale del numero di secondi specificato.</span><span class="sxs-lookup"><span data-stu-id="b9198-143">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="b9198-144">Il ritardo massimo consentito è 5 secondi. Se il valore è superiore a 5, viene generata una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="b9198-144">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="b9198-145">Come illustrato nell'esempio seguente, l'eccezione generata quando al metodo `GetMultipleAsync` viene passato il valore 6 viene sottoposta a wrapping in una <xref:System.AggregateException> dopo che il metodo `GetMultipleAsync` inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b9198-145">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

<span data-ttu-id="b9198-146">Come per l'iteratore di metodo, è possibile effettuare il refactoring del codice dell'esempio per eseguire la convalida prima di chiamare il metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="b9198-146">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="b9198-147">Come illustrato dall'output dell'esempio seguente, l'eccezione <xref:System.ArgumentOutOfRangeException> non viene sottoposta a wrapping in un'eccezione <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="b9198-147">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="see-also"></a><span data-ttu-id="b9198-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9198-148">See also</span></span>

- [<span data-ttu-id="b9198-149">Metodi</span><span class="sxs-lookup"><span data-stu-id="b9198-149">Methods</span></span>](methods.md)
