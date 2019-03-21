---
title: 'Procedura: usare un dizionario per archiviare istanze di evento - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845274"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="1342c-102">Procedura: usare un dizionario per archiviare istanze di evento (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1342c-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="1342c-103">Le funzioni di accesso a eventi personalizzati `add` e `remove` possono essere usate per esporre più eventi senza allocare un campo per ogni evento e usando invece un'istanza di <xref:System.Collections.Generic.Dictionary%602> per archiviare le istanze degli eventi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1342c-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="1342c-104">Ciò è utile solo se un tipo ha molti eventi, ma si prevede che la maggior parte di essi non verrà sottoscritta.</span><span class="sxs-lookup"><span data-stu-id="1342c-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="1342c-105">Questa implementazione è conforme al comportamento per [l'aggiunta e la rimozione dei delegati](~/_csharplang/spec/delegates.md#delegate-invocation) nella specifica del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="1342c-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="1342c-106">Si noti che l'istruzione [lock](../../language-reference/keywords/lock-statement.md) viene usata solo per *accedere* al dizionario con i gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="1342c-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="1342c-107">Non richiamare un gestore dell'evento nel corpo dell'istruzione `lock`, perché ciò potrebbe causare deadlock o conflitti di blocco.</span><span class="sxs-lookup"><span data-stu-id="1342c-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="1342c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1342c-108">See also</span></span>

- [<span data-ttu-id="1342c-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1342c-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1342c-110">Eventi</span><span class="sxs-lookup"><span data-stu-id="1342c-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="1342c-111">Delegati</span><span class="sxs-lookup"><span data-stu-id="1342c-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
