---
title: Clausola select - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: 68ea7ad6fc7cf5580dbdd0ae7f012f36566db0dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173510"
---
# <a name="select-clause-c-reference"></a>Clausola select (Riferimento C#)

In un'espressione di query, la clausola `select` specifica il tipo di valori che verranno prodotti quando viene eseguita la query. Il risultato è basato sulla valutazione di tutte le clausole precedenti e su qualsiasi espressione nella clausola `select` stessa. Un'espressione di query deve terminare con una clausola `select` o una clausola [group](group-clause.md).

Nell'esempio seguente viene illustrata una semplice clausola `select` in un'espressione di query.

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

Il tipo della sequenza prodotto dalla clausola `select` determina il tipo della variabile di query `queryHighScores`. Nel caso più semplice, la clausola `select` specifica solo la variabile di intervallo. In tal modo, la sequenza restituita contiene elementi dello stesso tipo dell'origine dati. Per ulteriori informazioni, vedere Relazioni tra tipi [in Operazioni di query LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Tuttavia, la clausola `select` fornisce anche un potente meccanismo per la trasformazione (o la *proiezione*) dell'origine dati in nuovi tipi. Per altre informazioni, vedere [Trasformazioni dati con LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).

## <a name="example"></a>Esempio

Nell'esempio seguente sono illustrate tutte le diverse forme che una clausola `select` può avere. In ogni query prendere nota della relazione tra `select` la `studentQuery2`clausola e il tipo della variabile di *query* (`studentQuery1`, e così via).

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

Come illustrato in `studentQuery8` nell'esempio precedente, in alcuni casi è preferibile che gli elementi della sequenza restituita contengano solo un subset delle proprietà degli elementi di origine. Riducendo al minimo le dimensioni della sequenza restituita, è possibile ridurre i requisiti di memoria e aumentare la velocità di esecuzione della query. A tale scopo, è possibile creare un tipo anonimo nella clausola `select` e usare un inizializzatore di oggetto per inizializzarlo con le proprietà appropriate dall'elemento di origine. Per un esempio di come eseguire questa operazione, vedere [Inizializzatori di oggetto e di raccolta](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="remarks"></a>Osservazioni

In fase di compilazione, la clausola `select` viene convertita in una chiamata al metodo per l'operatore query standard <xref:System.Linq.Enumerable.Select%2A>.

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Parole chiave di query (LINQ)Query Keywords (LINQ)](query-keywords.md)
- [clausola from](from-clause.md)
- [parziale (Metodo) (Riferimenti per C#)](partial-method.md)
- [Tipi anonimi](../../programming-guide/classes-and-structs/anonymous-types.md)
- [LINQ in C#](../../linq/index.md)
- [Language Integrated Query (LINQ)](../../programming-guide/concepts/linq/index.md)
