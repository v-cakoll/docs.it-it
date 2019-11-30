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
# <a name="whats-new-in-f-47"></a>Novità di F# 4,7

F#4,7 aggiunge più miglioramenti al F# linguaggio.

## <a name="get-started"></a>Attività iniziali

F#4,7 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.

## <a name="language-version"></a>Versione del linguaggio

Il F# compilatore 4,7 introduce la possibilità di impostare la versione del linguaggio efficace tramite una proprietà nel file di progetto:

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

È possibile impostarlo sui valori `4.6`, `4.7`, `latest`e `preview`. Il valore predefinito è `latest`.

Se lo si imposta su `preview`, il compilatore attiverà tutte le F# funzionalità di anteprima implementate nel compilatore.

## <a name="implicit-yields"></a>Rese implicite

Non è più necessario applicare la parola chiave `yield` in matrici, elenchi, sequenze o espressioni di calcolo in cui è possibile dedurre il tipo. Nell'esempio seguente, entrambe le espressioni richiedono l'istruzione `yield` per ogni voce precedente alla F# 4,7:

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

Se si introduce una singola parola chiave `yield`, a ogni altro elemento deve essere applicato anche `yield`.

I rendimenti impliciti non vengono attivati quando vengono usati in un'espressione che usa anche `yield!` per eseguire un'operazione, ad esempio una sequenza appiattita. In questi casi è necessario continuare a utilizzare `yield` oggi.

## <a name="wildcard-identifiers"></a>Identificatori con caratteri jolly

Nel F# codice che coinvolge le classi, l'autoidentificatore deve essere sempre esplicito nelle dichiarazioni di membri. Tuttavia, nei casi in cui l'autoidentificatore non viene mai usato, è stato tradizionalmente usato per usare un doppio carattere di sottolineatura per indicare un autoidentificatore senza nome. È ora possibile usare un singolo carattere di sottolineatura:

```fsharp
type C() =
    member _.M() = ()
```

Questo vale anche per i cicli di `for`:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Rientro rientri

Prima del F# 4,7, i requisiti di rientro per il costruttore primario e gli argomenti membri statici richiedevano un rientro eccessivo. A questo punto è necessario un solo ambito di rientro:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
