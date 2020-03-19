---
title: Novità di F . 4.7 - Guida di F
description: Ottenere una panoramica delle nuove funzionalità disponibili in F .
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185868"
---
# <a name="whats-new-in-f-47"></a><span data-ttu-id="3d19b-103">Novità di F .</span><span class="sxs-lookup"><span data-stu-id="3d19b-103">What's new in F# 4.7</span></span>

<span data-ttu-id="3d19b-104">Il linguaggio F .</span><span class="sxs-lookup"><span data-stu-id="3d19b-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="3d19b-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="3d19b-105">Get started</span></span>

<span data-ttu-id="3d19b-106">Il linguaggio F . 4.7 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3d19b-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="3d19b-107">Per altre informazioni, [iniziare a usare F.](../get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="3d19b-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="3d19b-108">Versione del linguaggio</span><span class="sxs-lookup"><span data-stu-id="3d19b-108">Language version</span></span>

<span data-ttu-id="3d19b-109">Il compilatore f .</span><span class="sxs-lookup"><span data-stu-id="3d19b-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3d19b-110">È possibile impostarlo `4.6`sui `4.7` `latest`valori `preview`, , e .</span><span class="sxs-lookup"><span data-stu-id="3d19b-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="3d19b-111">Il valore predefinito è `latest`.</span><span class="sxs-lookup"><span data-stu-id="3d19b-111">The default is `latest`.</span></span>

<span data-ttu-id="3d19b-112">Se si imposta `preview`su , il compilatore attiverà tutte le funzionalità di anteprima di F, implementate nel compilatore.</span><span class="sxs-lookup"><span data-stu-id="3d19b-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="3d19b-113">Rendimenti impliciti</span><span class="sxs-lookup"><span data-stu-id="3d19b-113">Implicit yields</span></span>

<span data-ttu-id="3d19b-114">Non è più necessario `yield` applicare la parola chiave in matrici, elenchi, sequenze o espressioni di calcolo in cui il tipo può essere dedotto.</span><span class="sxs-lookup"><span data-stu-id="3d19b-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="3d19b-115">Nell'esempio seguente, entrambe `yield` le espressioni richiedevano l'istruzione per ogni voce precedente a F .</span><span class="sxs-lookup"><span data-stu-id="3d19b-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="3d19b-116">Se si introduce `yield` una singola parola chiave, deve essere `yield` applicato anche ogni altro elemento.</span><span class="sxs-lookup"><span data-stu-id="3d19b-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="3d19b-117">I rendimenti impliciti non vengono attivati `yield!` quando vengono utilizzati in un'espressione che usa anche per eseguire un'operazione come appiattire una sequenza.</span><span class="sxs-lookup"><span data-stu-id="3d19b-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="3d19b-118">È necessario continuare `yield` a utilizzare oggi in questi casi.</span><span class="sxs-lookup"><span data-stu-id="3d19b-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="3d19b-119">Identificatori con caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="3d19b-119">Wildcard identifiers</span></span>

<span data-ttu-id="3d19b-120">Nel codice F , che coinvolge le classi, l'autoidentificatore deve essere sempre esplicito nelle dichiarazioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="3d19b-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="3d19b-121">Ma nei casi in cui l'autoidentificatore non viene mai utilizzato, è stato tradizionalmente convenzione per utilizzare un doppio segno di sottolineatura per indicare un autoidentificatore senza nome.</span><span class="sxs-lookup"><span data-stu-id="3d19b-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="3d19b-122">È ora possibile utilizzare un singolo trattino di sottolineatura:You can now use a single underscore:</span><span class="sxs-lookup"><span data-stu-id="3d19b-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="3d19b-123">Questo vale `for` anche per i cicli:</span><span class="sxs-lookup"><span data-stu-id="3d19b-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="3d19b-124">Rilassamento dell'indentazione</span><span class="sxs-lookup"><span data-stu-id="3d19b-124">Indentation relaxations</span></span>

<span data-ttu-id="3d19b-125">Prima della versione 4.7 di F, i requisiti di rientro per gli argomenti del costruttore primario e del membro statico richiedevano un rientro eccessivo.</span><span class="sxs-lookup"><span data-stu-id="3d19b-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="3d19b-126">Ora richiedono solo un singolo ambito di rientro:</span><span class="sxs-lookup"><span data-stu-id="3d19b-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
