---
title: Novità di C# 7.2
description: Panoramica delle nuove funzionalità in C# 7.2.
ms.date: 08/16/2017
ms.openlocfilehash: a74afd7f073daa46328d60149e2dd90207420a80
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566189"
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="add8a-103">Novità di C# 7.2</span><span class="sxs-lookup"><span data-stu-id="add8a-103">What's new in C# 7.2</span></span>

<span data-ttu-id="add8a-104">C# 7.2 è un'altra Point Release che aggiunge numerose funzionalità utili.</span><span class="sxs-lookup"><span data-stu-id="add8a-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="add8a-105">Il tema centrale di questa versione è l'uso più efficiente dei tipi valore, evitando inutili copie o allocazioni.</span><span class="sxs-lookup"><span data-stu-id="add8a-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="add8a-106">Le funzionalità rimanenti sono piccole e utili.</span><span class="sxs-lookup"><span data-stu-id="add8a-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="add8a-107">C# 7.2 usa l'elemento di configurazione per la [selezione della versione del linguaggio](../language-reference/configure-language-version.md) per selezionare la versione del linguaggio del compilatore.</span><span class="sxs-lookup"><span data-stu-id="add8a-107">C# 7.2 uses the [language version selection](../language-reference/configure-language-version.md) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="add8a-108">Le nuove funzionalità relative al linguaggio in questa versione sono:</span><span class="sxs-lookup"><span data-stu-id="add8a-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="add8a-109">Semantica di riferimento con i tipi valore</span><span class="sxs-lookup"><span data-stu-id="add8a-109">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="add8a-110">Una combinazione di miglioramenti della sintassi che consentono l'utilizzo dei tipi valore tramite la semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="add8a-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="add8a-111">Argomenti denominati non finali</span><span class="sxs-lookup"><span data-stu-id="add8a-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="add8a-112">Gli argomenti denominati possono essere seguiti da argomenti posizionali.</span><span class="sxs-lookup"><span data-stu-id="add8a-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="add8a-113">Caratteri di sottolineatura iniziali nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="add8a-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="add8a-114">I valori letterali numerici possono ora includere caratteri di sottolineatura iniziali prima di qualsiasi cifra stampata.</span><span class="sxs-lookup"><span data-stu-id="add8a-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="add8a-115">Modificatore di accesso `private protected`</span><span class="sxs-lookup"><span data-stu-id="add8a-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="add8a-116">Il modificatore di accesso `private protected` consente l'accesso per le classi derivate nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="add8a-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="add8a-117">Semantica di riferimento con i tipi valore</span><span class="sxs-lookup"><span data-stu-id="add8a-117">Reference semantics with value types</span></span>

<span data-ttu-id="add8a-118">Le funzionalità del linguaggio introdotte nella versione 7.2 consentono di lavorare con i tipi valore usando allo stesso tempo la semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="add8a-118">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="add8a-119">Queste funzionalità sono state progettate per migliorare le prestazioni riducendo al minimo la copia dei tipi valore senza dover sostenere le allocazioni di memoria associate all'uso dei tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="add8a-119">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="add8a-120">Sono incluse le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="add8a-120">The features include:</span></span>

 - <span data-ttu-id="add8a-121">Il modificatore `in` per i parametri, per specificare che un argomento viene passato per riferimento, ma non modificato dal metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="add8a-121">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="add8a-122">Il modificatore `ref readonly` per i valori restituiti dai metodi, per indicare che un metodo restituisce il valore per riferimento, ma non consente scritture su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="add8a-122">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="add8a-123">La dichiarazione `readonly struct` per indicare che uno struct non è modificabile e deve essere passato come parametro `in` ai relativi metodi membro.</span><span class="sxs-lookup"><span data-stu-id="add8a-123">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="add8a-124">La dichiarazione `ref struct` per indicare che un tipo di struct accede direttamente alla memoria gestita e deve sempre essere allocato nello stack.</span><span class="sxs-lookup"><span data-stu-id="add8a-124">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="add8a-125">Per altre informazioni su tutte queste modifiche, vedere [Semantica di riferimento con tipi di valore](../reference-semantics-with-value-types.md).</span><span class="sxs-lookup"><span data-stu-id="add8a-125">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="add8a-126">Argomenti denominati non finali</span><span class="sxs-lookup"><span data-stu-id="add8a-126">Non-trailing named arguments</span></span>

<span data-ttu-id="add8a-127">Per le chiamate di metodi è ora possibile usare argomenti denominati che precedono gli argomenti posizionali quando questi argomenti denominati sono nelle posizioni corrette.</span><span class="sxs-lookup"><span data-stu-id="add8a-127">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="add8a-128">Per altre informazioni, vedere [Argomenti denominati e facoltativi](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="add8a-128">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="add8a-129">Caratteri di sottolineatura iniziali nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="add8a-129">Leading underscores in numeric literals</span></span>

<span data-ttu-id="add8a-130">L'implementazione del supporto per i separatori di cifre in C# 7.0 non consentiva l'uso di `_` come primo carattere del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="add8a-130">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="add8a-131">I valori letterali numerici esadecimali e binari possono ora iniziare con `_`.</span><span class="sxs-lookup"><span data-stu-id="add8a-131">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="add8a-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="add8a-132">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="add8a-133">Modificatore di accesso _private protected_</span><span class="sxs-lookup"><span data-stu-id="add8a-133">_private protected_ access modifier</span></span>

<span data-ttu-id="add8a-134">Infine, il nuovo modificatore di accesso composto `private protected` indica che un membro è accessibile dalla classe che lo contiene o dalle classi derivate dichiarate nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="add8a-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="add8a-135">Anche se `protected internal` consente l'accesso da classi derivate o classi nello stesso assembly, `private protected` limita l'accesso ai tipi derivati dichiarati nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="add8a-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="add8a-136">Per altre informazioni, vedere [Modificatori di accesso](../language-reference/keywords/access-modifiers.md) nelle informazioni di riferimento sul linguaggio.</span><span class="sxs-lookup"><span data-stu-id="add8a-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
