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
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procedura: usare un dizionario per archiviare istanze di evento (Guida per programmatori C#)

Le funzioni di accesso a eventi personalizzati `add` e `remove` possono essere usate per esporre più eventi senza allocare un campo per ogni evento e usando invece un'istanza di <xref:System.Collections.Generic.Dictionary%602> per archiviare le istanze degli eventi, come illustrato nell'esempio seguente. Ciò è utile solo se un tipo ha molti eventi, ma si prevede che la maggior parte di essi non verrà sottoscritta.

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

Questa implementazione è conforme al comportamento per [l'aggiunta e la rimozione dei delegati](~/_csharplang/spec/delegates.md#delegate-invocation) nella specifica del linguaggio C#.

Si noti che l'istruzione [lock](../../language-reference/keywords/lock-statement.md) viene usata solo per *accedere* al dizionario con i gestori di eventi. Non richiamare un gestore dell'evento nel corpo dell'istruzione `lock`, perché ciò potrebbe causare deadlock o conflitti di blocco.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Eventi](../../../csharp/programming-guide/events/index.md)
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
