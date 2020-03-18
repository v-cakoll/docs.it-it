---
title: Archiviare i risultati di una query in memoria
description: Come archiviare i risultati.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 66a7a95c74db4062e76c54d4339ccb7343f44067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "65633560"
---
# <a name="store-the-results-of-a-query-in-memory"></a>Archiviare i risultati di una query in memoria

Una query è fondamentalmente un set di istruzioni per il recupero e l'organizzazione dei dati. Le query vengono eseguite in modalità lazy poiché viene richiesto ogni elemento successivo nel risultato. Quando si usa `foreach` per scorrere i risultati, gli elementi vengono restituiti quando ne viene eseguito l'accesso. Per valutare una query e archiviare i risultati senza eseguire un ciclo di `foreach`, è sufficiente chiamare uno dei seguenti metodi sulla variabile di query:

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 Quando si archiviano i risultati della query, assegnare l'oggetto Collection restituito a una nuova variabile, come illustrato nell'esempio seguente:

## <a name="example"></a>Esempio

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a>Vedere anche

- [Language Integrated Query (LINQ)](index.md)
