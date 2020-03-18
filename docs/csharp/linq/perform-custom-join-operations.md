---
title: Eseguire operazioni di join personalizzate (LINQ in C#)
description: Informazioni su come eseguire operazioni di join LINQ personalizzate in C#.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659852"
---
# <a name="perform-custom-join-operations"></a>Eseguire operazioni di join personalizzate

Questo esempio descrive come eseguire operazioni di join personalizzate non possibili con la clausola `join`. In un'espressione di query la clausola `join` è limitata e ottimizzata per gli equijoin che sono in assoluto il tipo più comune di operazione di join. Quando si esegue un equijoin, è quasi sempre possibile ottenere le prestazioni migliori usando la clausola `join`.

Non è tuttavia possibile usare la clausola `join` nei casi seguenti:

- Quando il join viene affermato su un'espressione di ineguaglianza (un non equijoin).

- Quando il join viene affermato su più di un'espressione di eguaglianza o di ineguaglianza.

- Quando è necessario introdurre una variabile di intervallo temporanea per la sequenza del lato destro (interno) prima dell'operazione di join.

 Per eseguire join che non sono equijoin, è possibile usare più clausole `from` per introdurre ogni origine dati in modo indipendente. Si applica quindi un'espressione di predicato in una clausola `where` alla variabile di intervallo per ogni origine. L'espressione può inoltre avere il formato di una chiamata al metodo.

> [!NOTE]
> Non confondere questo tipo di operazione di join personalizzata con l'uso di più clausole `from` per accedere a raccolte interne. Per ulteriori informazioni, vedere [Clausola join](../language-reference/keywords/join-clause.md).

## <a name="example"></a>Esempio

Il primo metodo nell'esempio seguente illustra un cross join semplice. I cross join devono essere usati con attenzione perché possono produrre set di risultati molto grandi. Tuttavia, possono essere utili in alcuni scenari per la creazione di sequenze di origine in cui eseguire query aggiuntive.

Il secondo metodo produce una sequenza di tutti i prodotti il cui ID categoria è incluso nell'elenco di categorie sul lato sinistro. Si noti l'uso della clausola `let` e del metodo `Contains` per creare una matrice temporanea. È anche possibile creare la matrice prima della query ed eliminare la prima clausola `from`.

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a>Esempio

Nell'esempio seguente la query deve creare un join di due sequenze basate su chiavi corrispondenti che, nel caso della sequenza interna (lato destro), non possono essere ottenute prima della clausola join stessa. Se il join viene eseguito con una clausola `join`, il metodo `Split` dovrà essere chiamato per ogni elemento. L'uso di più clausole `from` consente alla query di evitare l'overhead della chiamata al metodo ripetuta. Tuttavia, poiché `join` è ottimizzata, in questo caso particolare potrebbe risultare ancora più veloce rispetto all'uso di più clausole `from`. I risultati varieranno principalmente in base al costo in termini di utilizzo della chiamata al metodo.

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
- [clausola join](../language-reference/keywords/join-clause.md)
- [Ordinare i risultati di una clausola join](order-the-results-of-a-join-clause.md)
