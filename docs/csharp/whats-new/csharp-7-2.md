---
title: "Novità di c# 7.2"
description: "Panoramica delle nuove funzionalità in c# 7.2."
keywords: Progettazione del linguaggio c#, 7.2, Visual Studio 2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="20b30-104">Novità di c# 7.2</span><span class="sxs-lookup"><span data-stu-id="20b30-104">What's new in C# 7.2</span></span>

<span data-ttu-id="20b30-105">7.2 c# è un altro punto di rilascio che aggiunge il numero di funzionalità utili.</span><span class="sxs-lookup"><span data-stu-id="20b30-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="20b30-106">Un tema per questa versione funziona in modo più efficiente con tipi di valore, evitando inutili copie o le allocazioni.</span><span class="sxs-lookup"><span data-stu-id="20b30-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="20b30-107">Le funzionalità rimanenti sono piccole, nice hanno funzionalità.</span><span class="sxs-lookup"><span data-stu-id="20b30-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="20b30-108">7.2 c# utilizza il [selezione della lingua versione](csharp-7-1.md#language-version-selection) elemento di configurazione per selezionare la lingua del compilatore.</span><span class="sxs-lookup"><span data-stu-id="20b30-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="20b30-109">Le nuove funzionalità del linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="20b30-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="20b30-110">Semantica di riferimento con tipi di valore</span><span class="sxs-lookup"><span data-stu-id="20b30-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="20b30-111">Una combinazione di miglioramenti di sintassi che consentono l'utilizzo di tipi di valore utilizzando la semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="20b30-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="20b30-112">Argomenti denominati finali non</span><span class="sxs-lookup"><span data-stu-id="20b30-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="20b30-113">Argomenti denominati possono essere seguiti da argomenti posizionali.</span><span class="sxs-lookup"><span data-stu-id="20b30-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="20b30-114">Caratteri di sottolineatura iniziali nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="20b30-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="20b30-115">Valori letterali numerici possono ora includere caratteri di sottolineatura iniziali prima delle cifre stampate.</span><span class="sxs-lookup"><span data-stu-id="20b30-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="20b30-116">`private protected`modificatore di accesso</span><span class="sxs-lookup"><span data-stu-id="20b30-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="20b30-117">Il `private protected` modificatore di accesso consente l'accesso per le classi derivate nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="20b30-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="20b30-118">Semantica di riferimento con tipi di valore</span><span class="sxs-lookup"><span data-stu-id="20b30-118">Reference semantics with value types</span></span>

<span data-ttu-id="20b30-119">Funzionalità del linguaggio introdotte in 7.2 consentono di lavorare con i tipi di valore quando si utilizza la semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="20b30-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="20b30-120">Essi sono progettati per migliorare le prestazioni riducendo al minimo la copia tipi di valore senza incorrere nelle allocazioni di memoria associate all'utilizzo di tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="20b30-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="20b30-121">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="20b30-121">The features include:</span></span>

 - <span data-ttu-id="20b30-122">Il `in` modificatore sui parametri, per specificare che un argomento è passato per riferimento, ma non è stato modificato dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="20b30-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="20b30-123">Il `ref readonly` modificatore nel metodo restituisce, per indicare che un metodo restituisce il valore per riferimento, ma non consentire la scrittura in quell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="20b30-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="20b30-124">Il `readonly struct` dichiarazione, per indicare che una struttura non è modificabile e deve essere passata come un `in` parametro ai relativi metodi membro.</span><span class="sxs-lookup"><span data-stu-id="20b30-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="20b30-125">Il `ref struct` dichiarazione, per indicare che un tipo di struct accede direttamente alla memoria gestita e deve sempre essere stack allocato.</span><span class="sxs-lookup"><span data-stu-id="20b30-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="20b30-126">Per ulteriori informazioni su tutte queste modifiche nel [utilizzo di tipi di valore con la semantica di riferimento](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="20b30-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="20b30-127">Argomenti denominati finali non</span><span class="sxs-lookup"><span data-stu-id="20b30-127">Non-trailing named arguments</span></span>

<span data-ttu-id="20b30-128">Chiamate al metodo è ora possono utilizzare argomenti denominati che precedono gli argomenti posizionali quando questi argomenti sono nelle posizioni corrette.</span><span class="sxs-lookup"><span data-stu-id="20b30-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="20b30-129">Per ulteriori informazioni vedere [argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="20b30-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="20b30-130">Caratteri di sottolineatura iniziali nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="20b30-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="20b30-131">L'implementazione del supporto per i separatori di cifre in c# 7.0 non ha consentito di `_` sia il primo carattere del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="20b30-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="20b30-132">Esadecimale e valori letterali numerici binari ora possono iniziare con un `_`.</span><span class="sxs-lookup"><span data-stu-id="20b30-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="20b30-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20b30-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="20b30-134">Infine, un nuovo modificatore di accesso composta: `private protected` indica che un membro sono accessibili dalle classi derivate che vengono dichiarate nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="20b30-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="20b30-135">Mentre `protected internal` consente l'accesso da classi derivate o le classi che sono nello stesso assembly, `private protected` limita l'accesso ai tipi derivati dichiarato nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="20b30-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="20b30-136">Per ulteriori informazioni vedere [modificatori di accesso](../language-reference/keywords/access-modifiers.md) nella Guida di riferimento.</span><span class="sxs-lookup"><span data-stu-id="20b30-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
