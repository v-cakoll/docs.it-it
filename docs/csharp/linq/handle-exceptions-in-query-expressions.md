---
title: Gestire le eccezioni nelle espressioni di query (LINQ in C#)
description: Informazioni su come gestire le eccezioni nelle espressioni di query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: f900669412026e69598d3939c51ff8208b51b7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688501"
---
# <a name="handle-exceptions-in-query-expressions"></a>Gestire le eccezioni nelle espressioni di query

Nel contesto di un'espressione di query è possibile chiamare qualsiasi metodo. È tuttavia consigliabile non chiamare in un'espressione di query i metodi che possono creare un effetto collaterale, ad esempio la modifica del contenuto dell'origine dati o la generazione di un'eccezione. Questo esempio illustra come evitare di generare eccezioni quando si chiamano i metodi in un'espressione di query senza violare le linee guida generali di .NET sulla gestione delle eccezioni. Tali linee guida stabiliscono che è accettabile intercettare un'eccezione specifica quando è evidente il motivo per cui viene generata in un contesto specificato. Per altre informazioni, vedere [Suggerimenti per le eccezioni](../../standard/exceptions/best-practices-for-exceptions.md).

Nell'esempio finale viene illustrato come gestire quei casi in cui è necessario generare un'eccezione durante l'esecuzione di una query.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come spostare codice di gestione dell'eccezione al di fuori di un'espressione di query. Questa operazione è possibile solo quando il metodo non dipende da variabili locali per la query.

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a>Esempio

In alcuni casi la migliore risposta a un'eccezione generata all'interno di una query potrebbe essere l'arresto immediato dell'esecuzione della query. Nell'esempio seguente viene illustrato come gestire le eccezioni che potrebbero essere generate all'interno del corpo di una query. Si supponga che `SomeMethodThatMightThrow` possa potenzialmente generare un'eccezione che richiede l'arresto dell'esecuzione della query.

Si noti che il blocco `try` racchiude il ciclo `foreach` e non la query stessa, in quanto il ciclo `foreach` è il punto in corrispondenza del quale la query viene effettivamente eseguita. Per altre informazioni, vedere [Introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
