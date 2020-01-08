---
title: Delegati C# - Panoramica del linguaggio C#
description: Informazioni sull'associazione tardiva con delegati C#
ms.date: 08/10/2016
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: 317d3ee6fb1350824fa9b3b4d0e3e851780ce4d4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346875"
---
# <a name="delegates"></a>Delegati

Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari. I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri. I delegati sono simili al concetto di puntatori a funzione disponibili in altri linguaggi. A differenza dei puntatori a funzione, tuttavia, i delegati sono orientati agli oggetti e indipendenti dai tipi.

Nell'esempio seguente viene dichiarato e usato un tipo delegato denominato `Function`.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Un'istanza del tipo delegato `Function` può fare riferimento a qualsiasi metodo che accetta un argomento `double` e restituisce un valore `double`. Il metodo `Apply` applica una funzione specificata agli elementi di un `double[]`, restituendo un `double[]` con i risultati. Nel metodo `Main`, `Apply` viene usato per applicare a `double[]` tre funzioni differenti.

Un delegato può fare riferimento a un metodo statico, come `Square` o `Math.Sin` nell'esempio precedente, o a un metodo di istanza, come `m.Multiply` nell'esempio precedente. Un delegato che fa riferimento a un metodo di istanza fa riferimento anche a un oggetto particolare. Quando il metodo di istanza viene richiamato tramite il delegato, l'oggetto diventa `this` nella chiamata.

I delegati possono essere creati anche mediante funzioni anonime, ovvero "metodi inline" creati in tempo reale. Le funzioni anonime possono vedere le variabili locali dei metodi circostanti. Di conseguenza, il precedente esempio di moltiplicatore può essere scritto più facilmente senza usare una classe Multiplier:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Una proprietà interessante e utile di un delegato consiste nel fatto che non conosce o non prende in considerazione la classe del metodo a cui fa riferimento. Ciò che conta è che il metodo a cui un delegato fa riferimento abbia gli stessi parametri e restituisca lo stesso tipo del delegato in questione.

>[!div class="step-by-step"]
>[Precedente](interfaces.md)
>[Successivo](attributes.md)
