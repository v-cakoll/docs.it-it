---
title: Novità di C# 7.3
description: Panoramica delle nuove funzionalità in C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: 921374773d57d3fa6f8dd614f2691d345cf6eab7
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42907734"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="beb3a-103">Novità di C# 7.3</span><span class="sxs-lookup"><span data-stu-id="beb3a-103">What's new in C# 7.3</span></span>

<span data-ttu-id="beb3a-104">Esistono due temi principali per C# versione 7.3.</span><span class="sxs-lookup"><span data-stu-id="beb3a-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="beb3a-105">Un tema comprende funzionalità che consentono al codice gestito di offrire prestazioni altrettanto elevate di quelle del codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="beb3a-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="beb3a-106">Il secondo tema comprende miglioramenti incrementali delle funzionalità esistenti.</span><span class="sxs-lookup"><span data-stu-id="beb3a-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="beb3a-107">Inoltre, in questa versione sono state aggiunte nuove opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="beb3a-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="beb3a-108">Le nuove funzionalità seguenti supportano il tema del miglioramento delle prestazioni per il codice gestito:</span><span class="sxs-lookup"><span data-stu-id="beb3a-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="beb3a-109">È possibile accedere a campi fissi senza blocco.</span><span class="sxs-lookup"><span data-stu-id="beb3a-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="beb3a-110">È possibile riassegnare le variabili locali `ref`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="beb3a-111">È possibile usare gli inizializzatori nelle matrici `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="beb3a-112">È possibile usare istruzioni `fixed` con qualsiasi tipo che supporta un modello.</span><span class="sxs-lookup"><span data-stu-id="beb3a-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="beb3a-113">È possibile usare vincoli generici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="beb3a-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="beb3a-114">Sono stati apportati i miglioramenti seguenti alle funzionalità esistenti:</span><span class="sxs-lookup"><span data-stu-id="beb3a-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="beb3a-115">È possibile testare `==` e `!=` con i tipi di tupla.</span><span class="sxs-lookup"><span data-stu-id="beb3a-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="beb3a-116">È possibile usare le variabili di espressione in più posizioni.</span><span class="sxs-lookup"><span data-stu-id="beb3a-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="beb3a-117">È possibile associare gli attributi al campo sottostante delle proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="beb3a-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="beb3a-118">È stata migliorata la risoluzione del metodo quando gli argomenti sono diversi da `in`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="beb3a-119">La risoluzione dell'overload ora presenta un minor numero di casi ambigui.</span><span class="sxs-lookup"><span data-stu-id="beb3a-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="beb3a-120">Le nuove opzioni del compilatore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="beb3a-120">The new compiler options are:</span></span>

- <span data-ttu-id="beb3a-121">`-publicsign` per abilitare la firma degli assembly con software open source.</span><span class="sxs-lookup"><span data-stu-id="beb3a-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="beb3a-122">`-pathmap` per fornire un mapping per le directory di origine.</span><span class="sxs-lookup"><span data-stu-id="beb3a-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="beb3a-123">Il resto di questo articolo fornisce informazioni dettagliate e collegamenti a risorse aggiuntive per ciascuno dei miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="beb3a-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span>

## <a name="enabling-more-performant-safe-code"></a><span data-ttu-id="beb3a-124">Miglioramento delle prestazioni del codice gestito</span><span class="sxs-lookup"><span data-stu-id="beb3a-124">Enabling more performant safe code</span></span>

<span data-ttu-id="beb3a-125">È possibile scrivere codice C# in modo gestito con prestazioni altrettanto elevate di quelle del codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="beb3a-125">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="beb3a-126">Il codice gestito evita classi di errori come sovraccarichi del buffer, puntatori errati e altri errori di accesso alla memoria.</span><span class="sxs-lookup"><span data-stu-id="beb3a-126">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="beb3a-127">Queste nuove funzionalità espandono le capacità del codice gestito verificabile.</span><span class="sxs-lookup"><span data-stu-id="beb3a-127">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="beb3a-128">È possibile scrivere una parte più ampia del codice usando costrutti gestiti.</span><span class="sxs-lookup"><span data-stu-id="beb3a-128">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="beb3a-129">Queste funzionalità rendono più semplice tale attività.</span><span class="sxs-lookup"><span data-stu-id="beb3a-129">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="beb3a-130">I campi di indicizzazione `fixed` non richiedono il blocco</span><span class="sxs-lookup"><span data-stu-id="beb3a-130">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="beb3a-131">Si prenda in considerazione lo struct seguente:</span><span class="sxs-lookup"><span data-stu-id="beb3a-131">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="beb3a-132">Nelle versioni precedenti di C# era necessario bloccare una variabile per accedere a uno dei valori Integer che fanno parte di `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-132">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="beb3a-133">Ora è possibile usare il codice seguente per eseguire la compilazione in un contesto sicuro:</span><span class="sxs-lookup"><span data-stu-id="beb3a-133">Now, the following code compiles in a safe context:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="beb3a-134">La variabile `p` accede a un elemento `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-134">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="beb3a-135">Non è necessario dichiarare una variabile `int*` distinta.</span><span class="sxs-lookup"><span data-stu-id="beb3a-135">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="beb3a-136">Si noti che è comunque necessario un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-136">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="beb3a-137">Nelle versioni precedenti di C# era necessario dichiarare un secondo puntatore fisso:</span><span class="sxs-lookup"><span data-stu-id="beb3a-137">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="beb3a-138">Per altre informazioni, vedere l'articolo sull'[istruzione `fixed`](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-138">Fore more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="beb3a-139">Le variabili locali `ref` possono essere riassegnate</span><span class="sxs-lookup"><span data-stu-id="beb3a-139">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="beb3a-140">Ora è possibile riassegnare le variabili locali `ref` per fare riferimento a istanze diverse dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="beb3a-140">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="beb3a-141">Il codice seguente ora consente di eseguire la compilazione:</span><span class="sxs-lookup"><span data-stu-id="beb3a-141">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="beb3a-142">Per altre informazioni, vedere l'articolo sui [valori restituiti `ref` e le variabili locali `ref`](../programming-guide/classes-and-structs/ref-returns.md), oltre all'articolo su [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-142">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="beb3a-143">Le matrici `stackalloc` supportano gli inizializzatori</span><span class="sxs-lookup"><span data-stu-id="beb3a-143">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="beb3a-144">In precedenza era possibile specificare i valori per gli elementi in una matrice al momento dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="beb3a-144">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="beb3a-145">Ora la stessa sintassi può essere applicata alle matrici dichiarate con `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="beb3a-145">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="beb3a-146">Per altre informazioni, vedere l'articolo sull'[istruzione `stackalloc`](../language-reference/keywords/stackalloc.md) nelle informazioni di riferimento sul linguaggio.</span><span class="sxs-lookup"><span data-stu-id="beb3a-146">For more information, see the [`stackalloc` statement](../language-reference/keywords/stackalloc.md) article in the language reference.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="beb3a-147">L'istruzione `fixed` è supportata da più tipi</span><span class="sxs-lookup"><span data-stu-id="beb3a-147">More types support the `fixed` statement</span></span>

<span data-ttu-id="beb3a-148">L'istruzione `fixed` supportava un set di tipi limitato.</span><span class="sxs-lookup"><span data-stu-id="beb3a-148">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="beb3a-149">A partire da C# 7.3, qualsiasi tipo che contiene un metodo `GetPinnableReference()` che restituisce `ref T` oppure `ref readonly T` può essere `fixed`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-149">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="beb3a-150">L'aggiunta di questa funzionalità implica che è possibile usare `fixed` con <xref:System.Span%601?displayProperty=nameWithType> e i tipi correlati.</span><span class="sxs-lookup"><span data-stu-id="beb3a-150">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="beb3a-151">Per altre informazioni, vedere l'articolo sull'[istruzione `fixed`](../language-reference/keywords/fixed-statement.md) nelle informazioni di riferimento sul linguaggio.</span><span class="sxs-lookup"><span data-stu-id="beb3a-151">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="beb3a-152">Miglioramento dei vincoli generici</span><span class="sxs-lookup"><span data-stu-id="beb3a-152">Enhanced generic constraints</span></span>

<span data-ttu-id="beb3a-153">Ora è possibile specificare il tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> come vincoli di classe di base per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="beb3a-153">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="beb3a-154">È anche possibile usare il nuovo vincolo `unmanaged` per specificare che un parametro di tipo deve essere un **tipo non gestito**.</span><span class="sxs-lookup"><span data-stu-id="beb3a-154">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="beb3a-155">Un **tipo non gestito** è un tipo che non è un tipo riferimento e non contiene alcun tipo riferimento a nessun livello di annidamento.</span><span class="sxs-lookup"><span data-stu-id="beb3a-155">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="beb3a-156">Per altre informazioni, vedere gli articoli su [vincoli generici `where`](../language-reference/keywords/where-generic-type-constraint.md) e [vincoli sui parametri di tipo](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-156">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="beb3a-157">Miglioramenti delle funzionalità esistenti</span><span class="sxs-lookup"><span data-stu-id="beb3a-157">Make existing features better</span></span>

<span data-ttu-id="beb3a-158">Il secondo tema comprende i miglioramenti delle funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="beb3a-158">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="beb3a-159">Queste funzionalità migliorano la produttività durante la creazione di codice in C#.</span><span class="sxs-lookup"><span data-stu-id="beb3a-159">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="beb3a-160">Le tuple supportano `==` e `!=`</span><span class="sxs-lookup"><span data-stu-id="beb3a-160">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="beb3a-161">I tipi di tupla di C# ora supportano `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-161">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="beb3a-162">Per altre informazioni, vedere la sezione relativa all'[uguaglianza](../tuples.md#equality-and-tuples) nell'articolo sulle [tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-162">Fore more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="beb3a-163">Associare gli attributi al campo sottostante per le proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="beb3a-163">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="beb3a-164">Questa sintassi ora è supportata:</span><span class="sxs-lookup"><span data-stu-id="beb3a-164">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="beb3a-165">L'attributo `SomeThingAboutFieldAttribute` viene applicato al campo sottostante generato dal compilatore per `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="beb3a-165">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="beb3a-166">Per altre informazioni, vedere la sezione relativa agli [attributi](../programming-guide/concepts/attributes/index.md) nella Guida per programmatori C#.</span><span class="sxs-lookup"><span data-stu-id="beb3a-166">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="beb3a-167">Risoluzione dell'overload del metodo `in`</span><span class="sxs-lookup"><span data-stu-id="beb3a-167">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="beb3a-168">Quando si aggiungeva il modificatore dell'argomento `in`, questi due metodi causavano un'ambiguità:</span><span class="sxs-lookup"><span data-stu-id="beb3a-168">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="beb3a-169">Ora l'overload in base al valore (il primo nell'esempio precedente) è migliore dalla versione con il riferimento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="beb3a-169">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="beb3a-170">Per chiamare la versione con l'argomento di riferimento di sola lettura, è necessario includere il modificatore `in` durante la chiamata del metodo.</span><span class="sxs-lookup"><span data-stu-id="beb3a-170">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="beb3a-171">Questo comportamento è stato implementato come una correzione di bug.</span><span class="sxs-lookup"><span data-stu-id="beb3a-171">This was implemented as a bug fix.</span></span> <span data-ttu-id="beb3a-172">Non si tratta più di una situazione ambigua anche quando la versione del linguaggio è impostata su "7.2".</span><span class="sxs-lookup"><span data-stu-id="beb3a-172">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="beb3a-173">Per altre informazioni, vedere l'articolo sul [modificatore di parametro `in`](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-173">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="beb3a-174">Estensione delle variabili di espressione negli inizializzatori</span><span class="sxs-lookup"><span data-stu-id="beb3a-174">Extend expression variables in initializers</span></span>

<span data-ttu-id="beb3a-175">La sintassi aggiunta in C# 7.0 per consentire le dichiarazioni di variabili `out` è stata estesa in modo da includere inizializzatori di campo, inizializzatori di proprietà, inizializzatori di costruttore e clausole di query.</span><span class="sxs-lookup"><span data-stu-id="beb3a-175">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="beb3a-176">Questo consente l'uso di codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="beb3a-176">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="beb3a-177">Miglioramento dei candidati per l'overload</span><span class="sxs-lookup"><span data-stu-id="beb3a-177">Improved overload candidates</span></span>

<span data-ttu-id="beb3a-178">In ogni versione, le regole di risoluzione dell'overload vengono aggiornate per gestire le situazioni in cui le chiamate di metodi ambigui presentano una scelta "ovvia".</span><span class="sxs-lookup"><span data-stu-id="beb3a-178">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="beb3a-179">Questa versione aggiunge tre nuove regole per aiutare il compilatore a selezionare la scelta ovvia:</span><span class="sxs-lookup"><span data-stu-id="beb3a-179">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="beb3a-180">Quando un gruppo di metodi contiene sia membri di istanza che membri statici, il compilatore ignora i membri di istanza se il metodo è stato richiamato senza un contesto o un ricevitore di istanza.</span><span class="sxs-lookup"><span data-stu-id="beb3a-180">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="beb3a-181">Se il metodo è stato richiamato con un ricevitore di istanza, il compilatore ignora i membri statici.</span><span class="sxs-lookup"><span data-stu-id="beb3a-181">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="beb3a-182">Quando non è presente alcun ricevitore, il compilatore include solo i membri statici in un contesto statico. In caso contrario, include sia i membri statici che quelli di istanza.</span><span class="sxs-lookup"><span data-stu-id="beb3a-182">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="beb3a-183">Quando il ricevitore è in modo ambiguo un'istanza o un tipo, il compilatore include entrambi.</span><span class="sxs-lookup"><span data-stu-id="beb3a-183">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="beb3a-184">Un contesto statico, in cui non è possibile usare un ricevitore di istanza `this` implicito, include il corpo dei membri in cui non è definito `this`, ad esempio i membri statici, nonché i punti in cui non può essere usato `this`, ad esempio gli inizializzatori di campo e gli inizializzatori di costruttore.</span><span class="sxs-lookup"><span data-stu-id="beb3a-184">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="beb3a-185">Quando un gruppo di metodi include alcuni metodi generici i cui argomenti di tipo non soddisfano i vincoli, questi membri vengono rimossi dal set di candidati.</span><span class="sxs-lookup"><span data-stu-id="beb3a-185">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="beb3a-186">Per la conversione di un gruppo di metodi, i metodi candidati il cui tipo restituito non corrisponde al quello del delegato vengono rimossi dal set.</span><span class="sxs-lookup"><span data-stu-id="beb3a-186">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="beb3a-187">Sarà possibile notare questa modifica solo perché saranno presenti meno errori del compilatore per overload di metodi ambigui quando si sa con certezza quale metodo è preferibile.</span><span class="sxs-lookup"><span data-stu-id="beb3a-187">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="beb3a-188">Nuove opzioni del compilatore</span><span class="sxs-lookup"><span data-stu-id="beb3a-188">New compiler options</span></span>

<span data-ttu-id="beb3a-189">Le nuove opzioni del compilatore supportano nuovi scenari di compilazione e DevOps per i programmi in C#.</span><span class="sxs-lookup"><span data-stu-id="beb3a-189">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="beb3a-190">Firma pubblica o open source</span><span class="sxs-lookup"><span data-stu-id="beb3a-190">Public or Open Source signing</span></span>

<span data-ttu-id="beb3a-191">L'opzione del compilatore `-publicsign` indica al compilatore di firmare l'assembly usando una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="beb3a-191">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="beb3a-192">L'assembly viene contrassegnato come firmato, ma la firma proviene dalla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="beb3a-192">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="beb3a-193">Questa opzione consente di compilare assembly firmati da progetti open source con una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="beb3a-193">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="beb3a-194">Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -publicsign](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-194">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="beb3a-195">pathmap</span><span class="sxs-lookup"><span data-stu-id="beb3a-195">pathmap</span></span>

<span data-ttu-id="beb3a-196">L'opzione del compilatore `-pathmap` indica al compilatore di sostituire i percorsi di origine dall'ambiente di compilazione con i percorsi di origine mappati.</span><span class="sxs-lookup"><span data-stu-id="beb3a-196">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="beb3a-197">L'opzione `-pathmap` controlla il percorso di origine scritto dal compilatore nei file PDB o per <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="beb3a-197">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="beb3a-198">Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -pathmap](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="beb3a-198">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
