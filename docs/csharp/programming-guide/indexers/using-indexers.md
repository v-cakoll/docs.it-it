---
title: Uso di indicizzatori - Guida per programmatori C#
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: e742e4dd5ea92ec3baf37c915e024e713022b7b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416235"
---
# <a name="using-indexers-c-programming-guide"></a><span data-ttu-id="912c1-102">Uso di indicizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="912c1-102">Using indexers (C# Programming Guide)</span></span>

<span data-ttu-id="912c1-103">Gli indicizzatori sono una praticità sintattica che consente di creare una [classe](../../language-reference/keywords/class.md), uno [struct](../../language-reference/builtin-types/struct.md)o un' [interfaccia](../../language-reference/keywords/interface.md) a cui le applicazioni client possono accedere come matrice.</span><span class="sxs-lookup"><span data-stu-id="912c1-103">Indexers are a syntactic convenience that enable you to create a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) that client applications can access as an array.</span></span> <span data-ttu-id="912c1-104">Il compilatore genererà una `Item` Proprietà (o una proprietà denominata in alternativa se <xref:System.Runtime.CompilerServices.IndexerNameAttribute> è presente) e i metodi della funzione di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="912c1-104">The compiler will generate an `Item` property (or an alternatively named property if <xref:System.Runtime.CompilerServices.IndexerNameAttribute> is present), and the appropriate accessor methods.</span></span> <span data-ttu-id="912c1-105">Gli indicizzatori sono in genere implementati in tipi il cui scopo principale è incapsulare una raccolta o una matrice interna.</span><span class="sxs-lookup"><span data-stu-id="912c1-105">Indexers are most frequently implemented in types whose primary purpose is to encapsulate an internal collection or array.</span></span> <span data-ttu-id="912c1-106">Si supponga, ad esempio, di disporre di una classe `TempRecord` che rappresenta la temperatura in gradi Fahrenheit registrata in 10 ore diverse durante un periodo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="912c1-106">For example, suppose you have a class `TempRecord` that represents the temperature in Fahrenheit as recorded at 10 different times during a 24-hour period.</span></span> <span data-ttu-id="912c1-107">La classe contiene una `temps` matrice di tipo `float[]` in cui archiviare i valori di temperatura.</span><span class="sxs-lookup"><span data-stu-id="912c1-107">The class contains a `temps` array of type `float[]` to store the temperature values.</span></span> <span data-ttu-id="912c1-108">Implementando un indicizzatore in questa classe, i client possono accedere alle temperature in un'istanza `TempRecord` come `float temp = tempRecord[4]` invece che come `float temp = tempRecord.temps[4]`.</span><span class="sxs-lookup"><span data-stu-id="912c1-108">By implementing an indexer in this class, clients can access the temperatures in a `TempRecord` instance as `float temp = tempRecord[4]` instead of as `float temp = tempRecord.temps[4]`.</span></span> <span data-ttu-id="912c1-109">La notazione dell'indicizzatore non solo semplifica la sintassi per le applicazioni client. rende inoltre la classe e lo scopo più intuitivo per altri sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="912c1-109">The indexer notation not only simplifies the syntax for client applications; it also makes the class, and its purpose more intuitive for other developers to understand.</span></span>

<span data-ttu-id="912c1-110">Per dichiarare un indicizzatore in una classe o uno struct, usare la parola chiave [this](../../language-reference/keywords/this.md), come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="912c1-110">To declare an indexer on a class or struct, use the [this](../../language-reference/keywords/this.md) keyword, as the following example shows:</span></span>

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> <span data-ttu-id="912c1-111">La dichiarazione di un indicizzatore genererà automaticamente una proprietà denominata `Item` per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="912c1-111">Declaring an indexer will automatically generate a property named `Item` on the object.</span></span> <span data-ttu-id="912c1-112">La `Item` proprietà non è direttamente accessibile dall'espressione di [accesso ai membri](../../language-reference/operators/member-access-operators.md#member-access-expression-)dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="912c1-112">The `Item` property is not directly accessible from the instance [member access expression](../../language-reference/operators/member-access-operators.md#member-access-expression-).</span></span> <span data-ttu-id="912c1-113">Inoltre, se si aggiunge una `Item` proprietà personalizzata a un oggetto con un indicizzatore, si otterrà un [errore del compilatore CS0102](../../misc/cs0102.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-113">Additionally, if you add your own `Item` property to an object with an indexer, you'll get a [CS0102 compiler error](../../misc/cs0102.md).</span></span> <span data-ttu-id="912c1-114">Per evitare questo errore, usare <xref:System.Runtime.CompilerServices.IndexerNameAttribute> Rinomina l'indicizzatore come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="912c1-114">To avoid this error, use the <xref:System.Runtime.CompilerServices.IndexerNameAttribute> rename the indexer as detailed below.</span></span>

## <a name="remarks"></a><span data-ttu-id="912c1-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="912c1-115">Remarks</span></span>

<span data-ttu-id="912c1-116">Il tipo di un indicizzatore e dei relativi parametri deve essere accessibile almeno quanto l'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-116">The type of an indexer and the type of its parameters must be at least as accessible as the indexer itself.</span></span> <span data-ttu-id="912c1-117">Per altre informazioni sui livelli di accessibilità, vedere [Modificatori di accesso](../../language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-117">For more information about accessibility levels, see [Access Modifiers](../../language-reference/keywords/access-modifiers.md).</span></span>

<span data-ttu-id="912c1-118">Per altre informazioni sull'uso degli indicizzatori con un'interfaccia, vedere [Indicizzatori nelle interfacce](./indexers-in-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-118">For more information about how to use indexers with an interface, see [Interface Indexers](./indexers-in-interfaces.md).</span></span>

<span data-ttu-id="912c1-119">La firma di un indicizzatore è costituita dal numero e dai tipi dei relativi parametri formali.</span><span class="sxs-lookup"><span data-stu-id="912c1-119">The signature of an indexer consists of the number and types of its formal parameters.</span></span> <span data-ttu-id="912c1-120">Non include il tipo di indicizzatore o i nomi dei parametri formali.</span><span class="sxs-lookup"><span data-stu-id="912c1-120">It doesn't include the indexer type or the names of the formal parameters.</span></span> <span data-ttu-id="912c1-121">Se si dichiarano più indicizzatori nella stessa classe, gli indicizzatori devono avere firme diverse.</span><span class="sxs-lookup"><span data-stu-id="912c1-121">If you declare more than one indexer in the same class, they must have different signatures.</span></span>

<span data-ttu-id="912c1-122">Il valore di un indicizzatore non è classificato come una variabile, pertanto non è possibile passare il valore di un indicizzatore come un parametro [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-122">An indexer value is not classified as a variable; therefore, you cannot pass an indexer value as a [ref](../../language-reference/keywords/ref.md) or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter.</span></span>

<span data-ttu-id="912c1-123">Per fornire all'indicizzatore un nome che possa essere usato da altri linguaggi, usare <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="912c1-123">To provide the indexer with a name that other languages can use, use <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, as the following example shows:</span></span>

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

<span data-ttu-id="912c1-124">Questo indicizzatore avrà il nome `TheItem` , perché viene sottoposto a override dall'attributo del nome dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-124">This indexer will have the name `TheItem`, as it is overridden by the indexer name attribute.</span></span> <span data-ttu-id="912c1-125">Per impostazione predefinita, il nome dell'indicizzatore è `Item` .</span><span class="sxs-lookup"><span data-stu-id="912c1-125">By default, the indexer name is `Item`.</span></span>

## <a name="example-1"></a><span data-ttu-id="912c1-126">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="912c1-126">Example 1</span></span>

<span data-ttu-id="912c1-127">Nell'esempio seguente viene illustrato come dichiarare un campo di matrice privata, `temps`, e un indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-127">The following example shows how to declare a private array field, `temps`, and an indexer.</span></span> <span data-ttu-id="912c1-128">L'indicizzatore consente l'accesso diretto all'istanza `tempRecord[i]`.</span><span class="sxs-lookup"><span data-stu-id="912c1-128">The indexer enables direct access to the instance `tempRecord[i]`.</span></span> <span data-ttu-id="912c1-129">In alternativa all'uso dell'indicizzatore, è possibile dichiarare la matrice come un membro [public](../../language-reference/keywords/public.md) e accedere direttamente ai relativi membri, `tempRecord.temps[i]`.</span><span class="sxs-lookup"><span data-stu-id="912c1-129">The alternative to using the indexer is to declare the array as a [public](../../language-reference/keywords/public.md) member and access its members, `tempRecord.temps[i]`, directly.</span></span>

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

<span data-ttu-id="912c1-130">Si noti che quando viene valutato l'accesso di un indicizzatore, ad esempio in un'istruzione `Console.Write`, viene richiamata la funzione di accesso [get](../../language-reference/keywords/get.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-130">Notice that when an indexer's access is evaluated, for example, in a `Console.Write` statement, the [get](../../language-reference/keywords/get.md) accessor is invoked.</span></span> <span data-ttu-id="912c1-131">Pertanto, se non esiste alcuna funzione di accesso `get`, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="912c1-131">Therefore, if no `get` accessor exists, a compile-time error occurs.</span></span>

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a><span data-ttu-id="912c1-132">Indicizzazione tramite altri valori</span><span class="sxs-lookup"><span data-stu-id="912c1-132">Indexing using other values</span></span>

<span data-ttu-id="912c1-133">C# non limita il tipo del parametro dell'indicizzatore a Integer.</span><span class="sxs-lookup"><span data-stu-id="912c1-133">C# doesn't limit the indexer parameter type to integer.</span></span> <span data-ttu-id="912c1-134">Può ad esempio essere utile usare una stringa con un indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-134">For example, it may be useful to use a string with an indexer.</span></span> <span data-ttu-id="912c1-135">Un indicizzatore di questo tipo potrebbe essere implementato eseguendo la ricerca della stringa nella raccolta e restituendo il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="912c1-135">Such an indexer might be implemented by searching for the string in the collection, and returning the appropriate value.</span></span> <span data-ttu-id="912c1-136">Poiché è possibile eseguire l'overload delle funzioni di accesso, la stringa e le versioni integer possono coesistere.</span><span class="sxs-lookup"><span data-stu-id="912c1-136">As accessors can be overloaded, the string and integer versions can coexist.</span></span>

## <a name="example-2"></a><span data-ttu-id="912c1-137">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="912c1-137">Example 2</span></span>

<span data-ttu-id="912c1-138">L'esempio seguente dichiara una classe che archivia i giorni della settimana.</span><span class="sxs-lookup"><span data-stu-id="912c1-138">The following example declares a class that stores the days of the week.</span></span> <span data-ttu-id="912c1-139">Una funzione di accesso `get` accetta una stringa e il nome di un giorno e restituisce l'intero corrispondente.</span><span class="sxs-lookup"><span data-stu-id="912c1-139">A `get` accessor takes a string, the name of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="912c1-140">Ad esempio, "Domenica" restituisce 0, "Lunedì" restituisce 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="912c1-140">For example, "Sunday" returns 0, "Monday" returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a><span data-ttu-id="912c1-141">Utilizzo dell'esempio 2</span><span class="sxs-lookup"><span data-stu-id="912c1-141">Consuming example 2</span></span>

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a><span data-ttu-id="912c1-142">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="912c1-142">Example 3</span></span>

<span data-ttu-id="912c1-143">Nell'esempio seguente viene dichiarata una classe che archivia i giorni della settimana usando l' <xref:System.DayOfWeek?displayProperty=fullName> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="912c1-143">The following example declares a class that stores the days of the week using the <xref:System.DayOfWeek?displayProperty=fullName> enum.</span></span> <span data-ttu-id="912c1-144">Una `get` funzione di accesso accetta un oggetto `DayOfWeek` , il valore di un giorno e restituisce l'intero corrispondente.</span><span class="sxs-lookup"><span data-stu-id="912c1-144">A `get` accessor takes a `DayOfWeek`, the value of a day, and returns the corresponding integer.</span></span> <span data-ttu-id="912c1-145">Ad esempio, `DayOfWeek.Sunday` restituisce 0, `DayOfWeek.Monday` restituisce 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="912c1-145">For example, `DayOfWeek.Sunday` returns 0, `DayOfWeek.Monday` returns 1, and so on.</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a><span data-ttu-id="912c1-146">Utilizzo dell'esempio 3</span><span class="sxs-lookup"><span data-stu-id="912c1-146">Consuming example 3</span></span>

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a><span data-ttu-id="912c1-147">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="912c1-147">Robust programming</span></span>

<span data-ttu-id="912c1-148">Esistono due modi principali per migliorare la sicurezza e l'affidabilità degli indicizzatori:</span><span class="sxs-lookup"><span data-stu-id="912c1-148">There are two main ways in which the security and reliability of indexers can be improved:</span></span>

- <span data-ttu-id="912c1-149">Assicurarsi di incorporare qualche tipo di strategia di gestione degli errori per gestire la possibilità che il codice client passi un valore di indice non valido.</span><span class="sxs-lookup"><span data-stu-id="912c1-149">Be sure to incorporate some type of error-handling strategy to handle the chance of client code passing in an invalid index value.</span></span> <span data-ttu-id="912c1-150">Nel primo esempio riportato in questo argomento, la classe TempRecord fornisce una proprietà Length che consente al codice client di verificare l'input prima di passarlo all'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-150">In the first example earlier in this topic, the TempRecord class provides a Length property that enables the client code to verify the input before passing it to the indexer.</span></span> <span data-ttu-id="912c1-151">È anche possibile inserire il codice di gestione degli errori nell'indicizzatore stesso.</span><span class="sxs-lookup"><span data-stu-id="912c1-151">You can also put the error handling code inside the indexer itself.</span></span> <span data-ttu-id="912c1-152">Assicurarsi di documentare per gli utenti qualsiasi eccezione generata all'interno di una funzione di accesso dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="912c1-152">Be sure to document for users any exceptions that you throw inside an indexer accessor.</span></span>

- <span data-ttu-id="912c1-153">Impostare l'accessibilità delle funzioni di accesso [get](../../language-reference/keywords/get.md) e [set](../../language-reference/keywords/set.md) in modo che siano quanto più restrittive possibile.</span><span class="sxs-lookup"><span data-stu-id="912c1-153">Set the accessibility of the [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessors to be as restrictive as is reasonable.</span></span> <span data-ttu-id="912c1-154">Questo è particolarmente importante per la funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="912c1-154">This is important for the `set` accessor in particular.</span></span> <span data-ttu-id="912c1-155">Per altre informazioni, vedere [Limitazione dell'accessibilità delle funzioni di accesso](../classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="912c1-155">For more information, see [Restricting Accessor Accessibility](../classes-and-structs/restricting-accessor-accessibility.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="912c1-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="912c1-156">See also</span></span>

- [<span data-ttu-id="912c1-157">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="912c1-157">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="912c1-158">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="912c1-158">Indexers</span></span>](./index.md)
- [<span data-ttu-id="912c1-159">Proprietà</span><span class="sxs-lookup"><span data-stu-id="912c1-159">Properties</span></span>](../classes-and-structs/properties.md)
