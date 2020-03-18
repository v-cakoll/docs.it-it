---
title: Delegati C# - Panoramica del linguaggio C#
description: Informazioni sull'associazione tardiva con delegati C#
ms.date: 02/27/2020
ms.assetid: 3cc27357-3ac2-43a1-aad0-86a77b88f884
ms.openlocfilehash: b1740ddc65dcb0ee8775f4cbaa8356293ea55fae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78159169"
---
# <a name="delegates"></a>Delegati

Un ***tipo delegato*** rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari. I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri. I delegati sono simili al concetto di puntatori a funzione che si trova in altri linguaggi. A differenza dei puntatori a funzione, i delegati sono orientati agli oggetti e indipendenti dai tipi.

Nell'esempio seguente viene dichiarato e usato un tipo delegato denominato `Function`.

[!code-csharp[DelegateExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L3-L37)]

Un'istanza del tipo delegato `Function` può fare riferimento a qualsiasi metodo che accetta un argomento `double` e restituisce un valore `double`. Il metodo `Apply` applica una funzione specificata agli elementi di un `double[]`, restituendo un `double[]` con i risultati. Nel metodo `Main`, `Apply` viene usato per applicare a `double[]` tre funzioni differenti.

Un delegato può fare riferimento a un metodo statico, come `Square` o `Math.Sin` nell'esempio precedente, o a un metodo di istanza, come `m.Multiply` nell'esempio precedente. Un delegato che fa riferimento a un metodo di istanza fa riferimento anche a un oggetto particolare. Quando il metodo di istanza viene richiamato tramite il delegato, l'oggetto diventa `this` nella chiamata.

I delegati possono anche essere creati utilizzando funzioni anonime, ovvero "metodi inline" che vengono creati quando vengono dichiarati. Le funzioni anonime possono vedere le variabili locali dei metodi circostanti. L'esempio seguente non crea una classe:The following example doesn't create a class:

[!code-csharp[LambdaExample](../../../samples/snippets/csharp/tour/delegates/Program.cs#L44-L44)]

Un delegato non conosce né si preoccupa della classe del metodo a cui fa riferimento; tutto ciò che conta è che il metodo a cui si fa riferimento abbia gli stessi parametri e lo stesso tipo restituito del delegato.

>[!div class="step-by-step"]
>[Successivo](interfaces.md)
>[precedente](attributes.md)
