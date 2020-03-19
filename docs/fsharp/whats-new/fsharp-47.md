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
# <a name="whats-new-in-f-47"></a>Novità di F .

Il linguaggio F .

## <a name="get-started"></a>Introduzione

Il linguaggio F . 4.7 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per altre informazioni, [iniziare a usare F.](../get-started/index.md)

## <a name="language-version"></a>Versione del linguaggio

Il compilatore f .

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

È possibile impostarlo `4.6`sui `4.7` `latest`valori `preview`, , e . Il valore predefinito è `latest`.

Se si imposta `preview`su , il compilatore attiverà tutte le funzionalità di anteprima di F, implementate nel compilatore.

## <a name="implicit-yields"></a>Rendimenti impliciti

Non è più necessario `yield` applicare la parola chiave in matrici, elenchi, sequenze o espressioni di calcolo in cui il tipo può essere dedotto. Nell'esempio seguente, entrambe `yield` le espressioni richiedevano l'istruzione per ogni voce precedente a F .

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

Se si introduce `yield` una singola parola chiave, deve essere `yield` applicato anche ogni altro elemento.

I rendimenti impliciti non vengono attivati `yield!` quando vengono utilizzati in un'espressione che usa anche per eseguire un'operazione come appiattire una sequenza. È necessario continuare `yield` a utilizzare oggi in questi casi.

## <a name="wildcard-identifiers"></a>Identificatori con caratteri jolly

Nel codice F , che coinvolge le classi, l'autoidentificatore deve essere sempre esplicito nelle dichiarazioni dei membri. Ma nei casi in cui l'autoidentificatore non viene mai utilizzato, è stato tradizionalmente convenzione per utilizzare un doppio segno di sottolineatura per indicare un autoidentificatore senza nome. È ora possibile utilizzare un singolo trattino di sottolineatura:You can now use a single underscore:

```fsharp
type C() =
    member _.M() = ()
```

Questo vale `for` anche per i cicli:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Rilassamento dell'indentazione

Prima della versione 4.7 di F, i requisiti di rientro per gli argomenti del costruttore primario e del membro statico richiedevano un rientro eccessivo. Ora richiedono solo un singolo ambito di rientro:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
