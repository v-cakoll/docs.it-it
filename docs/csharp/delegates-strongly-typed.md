---
title: Delegati fortemente tipizzati
description: Informazioni su come usare i tipi delegati generici per dichiarare tipi personalizzati quando si crea una funzionalità che richiede i delegati.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: efdbef39d0e6bf2f07cde2c9621cec173e921752
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037351"
---
# <a name="strongly-typed-delegates"></a><span data-ttu-id="682bc-103">Delegati fortemente tipizzati</span><span class="sxs-lookup"><span data-stu-id="682bc-103">Strongly Typed Delegates</span></span>

[<span data-ttu-id="682bc-104">Precedente</span><span class="sxs-lookup"><span data-stu-id="682bc-104">Previous</span></span>](delegate-class.md)

<span data-ttu-id="682bc-105">Nell'articolo precedente è stata descritta la creazione di tipi di delegato specifici tramite la parola chiave `delegate`.</span><span class="sxs-lookup"><span data-stu-id="682bc-105">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span> 

<span data-ttu-id="682bc-106">La classe Delegate astratta offre l'infrastruttura per l'accoppiamento libero e la chiamata.</span><span class="sxs-lookup"><span data-stu-id="682bc-106">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="682bc-107">I tipi delegati concreti diventano più utili includendo e imponendo l'indipendenza dai tipi per i metodi aggiunti all'elenco di chiamate per un oggetto delegato.</span><span class="sxs-lookup"><span data-stu-id="682bc-107">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="682bc-108">Quando si usa la parola chiave `delegate` e si definisce un tipo delegato concreto, il compilatore genera tali metodi.</span><span class="sxs-lookup"><span data-stu-id="682bc-108">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="682bc-109">In pratica, verranno creati nuovi tipi delegati ogni volta che è necessaria una firma del metodo diversa.</span><span class="sxs-lookup"><span data-stu-id="682bc-109">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="682bc-110">Questa operazione potrebbe risultare tediosa dopo un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="682bc-110">This work could get tedious after a time.</span></span> <span data-ttu-id="682bc-111">Ogni nuova funzionalità richiede nuovi tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="682bc-111">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="682bc-112">Fortunatamente, questo non è necessario.</span><span class="sxs-lookup"><span data-stu-id="682bc-112">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="682bc-113">Il framework .NET Core include diversi tipi che è possibile riutilizzare quando sono necessari tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="682bc-113">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="682bc-114">Poiché si tratta di definizioni [generiche](programming-guide/generics/index.md) è possibile dichiarare personalizzazioni quando sono necessarie nuove dichiarazioni di metodi.</span><span class="sxs-lookup"><span data-stu-id="682bc-114">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span> 

<span data-ttu-id="682bc-115">Il primo di questi tipi è il tipo <xref:System.Action> e diverse variazioni:</span><span class="sxs-lookup"><span data-stu-id="682bc-115">The first of these types is the <xref:System.Action> type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="682bc-116">Il modificatore `in` nell'argomento di tipo generico è descritto nell'articolo sulla covarianza.</span><span class="sxs-lookup"><span data-stu-id="682bc-116">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="682bc-117">Sono disponibili variazioni del delegato `Action` che contengono fino a 16 argomenti, ad esempio <xref:System.Action%6016>.</span><span class="sxs-lookup"><span data-stu-id="682bc-117">There are variations of the `Action` delegate that contain up to 16 arguments such as <xref:System.Action%6016>.</span></span>
<span data-ttu-id="682bc-118">È importante che queste definizioni usino argomenti generici diversi per ogni argomento di delegato in modo da offrire la massima flessibilità.</span><span class="sxs-lookup"><span data-stu-id="682bc-118">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="682bc-119">Gli argomenti del metodo possono essere dello stesso tipo, ma non devono esserlo necessariamente.</span><span class="sxs-lookup"><span data-stu-id="682bc-119">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="682bc-120">Usare uno dei tipi `Action` per ogni tipo delegato con tipo restituito void.</span><span class="sxs-lookup"><span data-stu-id="682bc-120">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="682bc-121">Il framework include anche diversi tipi delegati generici che è possibile usare per i tipi delegati che restituiscono valori:</span><span class="sxs-lookup"><span data-stu-id="682bc-121">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="682bc-122">Il modificatore `out` nell'argomento di tipo generico del risultato è descritto nell'articolo sulla covarianza.</span><span class="sxs-lookup"><span data-stu-id="682bc-122">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="682bc-123">Sono disponibili variazioni del delegato `Func` che contengono fino a 16 argomenti di input, ad esempio <xref:System.Func%6017>.</span><span class="sxs-lookup"><span data-stu-id="682bc-123">There are variations of the `Func` delegate with up to 16 input arguments such as <xref:System.Func%6017>.</span></span>
<span data-ttu-id="682bc-124">Per convenzione, il tipo del risultato è sempre l'ultimo parametro di tipo in tutte le dichiarazioni `Func`.</span><span class="sxs-lookup"><span data-stu-id="682bc-124">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="682bc-125">Usare uno dei tipi `Func` per ogni tipo delegato che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="682bc-125">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="682bc-126">È disponibile anche una <xref:System.Predicate%601> specializzata</span><span class="sxs-lookup"><span data-stu-id="682bc-126">There's also a specialized <xref:System.Predicate%601></span></span> 
<span data-ttu-id="682bc-127">digitare per un delegato che restituisce un test su un singolo valore:</span><span class="sxs-lookup"><span data-stu-id="682bc-127">type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="682bc-128">È possibile notare che per ogni tipo `Predicate`, esiste un tipo `Func` strutturalmente equivalente, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="682bc-128">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="682bc-129">Si potrebbe pensare che questi due tipi siano equivalenti.</span><span class="sxs-lookup"><span data-stu-id="682bc-129">You might think these two types are equivalent.</span></span> <span data-ttu-id="682bc-130">Ma non lo sono.</span><span class="sxs-lookup"><span data-stu-id="682bc-130">They are not.</span></span>
<span data-ttu-id="682bc-131">Queste due variabili non possono essere usate indifferentemente.</span><span class="sxs-lookup"><span data-stu-id="682bc-131">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="682bc-132">A una variabile di un tipo non è possibile assegnare un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="682bc-132">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="682bc-133">Il sistema dei tipi di C# usa i nomi dei tipi definiti, non la struttura.</span><span class="sxs-lookup"><span data-stu-id="682bc-133">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="682bc-134">Tutte queste definizioni di tipi delegati nella libreria .NET Core dovrebbero eliminare la necessità di definire un nuovo tipo delegato per ogni nuova funzionalità creata che richiede delegati.</span><span class="sxs-lookup"><span data-stu-id="682bc-134">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="682bc-135">Queste definizioni generiche dovrebbero offrire tutti i tipi delegati necessari nella maggior parte delle situazioni.</span><span class="sxs-lookup"><span data-stu-id="682bc-135">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="682bc-136">È possibile creare semplicemente un'istanza di uno di questi tipi con i parametri di tipo richiesti.</span><span class="sxs-lookup"><span data-stu-id="682bc-136">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="682bc-137">Nel caso di algoritmi che possono essere definiti come generici, questi delegati possono essere usati come tipi generici.</span><span class="sxs-lookup"><span data-stu-id="682bc-137">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span> 

<span data-ttu-id="682bc-138">Ciò dovrebbe consentire di risparmiare tempo e di ridurre il numero di nuovi tipi da creare per usare i delegati.</span><span class="sxs-lookup"><span data-stu-id="682bc-138">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="682bc-139">Nel articolo successivo sono descritti diversi modelli comuni per l'uso pratico dei delegati.</span><span class="sxs-lookup"><span data-stu-id="682bc-139">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="682bc-140">avanti</span><span class="sxs-lookup"><span data-stu-id="682bc-140">Next</span></span>](delegates-patterns.md)
