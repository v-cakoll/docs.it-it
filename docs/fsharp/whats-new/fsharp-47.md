---
title: Novità di F# 4,7- F# Guida
description: Ottenere una panoramica delle nuove funzionalità disponibili in F# 4,7.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644068"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="52e51-103">Novità di F# 4,7</span><span class="sxs-lookup"><span data-stu-id="52e51-103">What's new in F# 4.7</span></span>

<span data-ttu-id="52e51-104">F#4,7 aggiunge più miglioramenti al F# linguaggio.</span><span class="sxs-lookup"><span data-stu-id="52e51-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="52e51-105">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="52e51-105">Get started</span></span>

<span data-ttu-id="52e51-106">F#4,7 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52e51-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="52e51-107">Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.</span><span class="sxs-lookup"><span data-stu-id="52e51-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="52e51-108">Versione del linguaggio</span><span class="sxs-lookup"><span data-stu-id="52e51-108">Language version</span></span>

<span data-ttu-id="52e51-109">Il F# compilatore 4,7 introduce la possibilità di impostare la versione del linguaggio efficace tramite una proprietà nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="52e51-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="52e51-110">È possibile impostarlo sui valori `4.6`, `4.7`, `latest`e `preview`.</span><span class="sxs-lookup"><span data-stu-id="52e51-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="52e51-111">Il valore predefinito è `latest`.</span><span class="sxs-lookup"><span data-stu-id="52e51-111">The default is `latest`.</span></span>

<span data-ttu-id="52e51-112">Se lo si imposta su `preview`, il compilatore attiverà tutte le F# funzionalità di anteprima implementate nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="52e51-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="52e51-113">Rese implicite</span><span class="sxs-lookup"><span data-stu-id="52e51-113">Implicit yields</span></span>

<span data-ttu-id="52e51-114">Non è più necessario applicare la parola chiave `yield` in matrici, elenchi, sequenze o espressioni di calcolo in cui è possibile dedurre il tipo.</span><span class="sxs-lookup"><span data-stu-id="52e51-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="52e51-115">Nell'esempio seguente, entrambe le espressioni richiedono l'istruzione `yield` per ogni voce precedente alla F# 4,7:</span><span class="sxs-lookup"><span data-stu-id="52e51-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [ 
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then 
            "Saturday"
            "Sunday"
    ] 
```

<span data-ttu-id="52e51-116">Se si introduce una singola parola chiave `yield`, a ogni altro elemento deve essere applicato anche `yield`.</span><span class="sxs-lookup"><span data-stu-id="52e51-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="52e51-117">I rendimenti impliciti non vengono attivati quando vengono usati in un'espressione che usa anche `yield!` per eseguire un'operazione, ad esempio una sequenza appiattita.</span><span class="sxs-lookup"><span data-stu-id="52e51-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="52e51-118">In questi casi è necessario continuare a utilizzare `yield` oggi.</span><span class="sxs-lookup"><span data-stu-id="52e51-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="52e51-119">Identificatori con caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="52e51-119">Wildcard identifiers</span></span>

<span data-ttu-id="52e51-120">Nel F# codice che coinvolge le classi, l'autoidentificatore deve essere sempre esplicito nelle dichiarazioni di membri.</span><span class="sxs-lookup"><span data-stu-id="52e51-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="52e51-121">Tuttavia, nei casi in cui l'autoidentificatore non viene mai usato, è stato tradizionalmente usato per usare un doppio carattere di sottolineatura per indicare un autoidentificatore senza nome.</span><span class="sxs-lookup"><span data-stu-id="52e51-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="52e51-122">È ora possibile usare un singolo carattere di sottolineatura:</span><span class="sxs-lookup"><span data-stu-id="52e51-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="52e51-123">Questo vale anche per i cicli di `for`:</span><span class="sxs-lookup"><span data-stu-id="52e51-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="52e51-124">Rientro rientri</span><span class="sxs-lookup"><span data-stu-id="52e51-124">Indentation relaxations</span></span>

<span data-ttu-id="52e51-125">Prima del F# 4,7, i requisiti di rientro per il costruttore primario e gli argomenti membri statici richiedevano un rientro eccessivo.</span><span class="sxs-lookup"><span data-stu-id="52e51-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="52e51-126">A questo punto è necessario un solo ambito di rientro:</span><span class="sxs-lookup"><span data-stu-id="52e51-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
