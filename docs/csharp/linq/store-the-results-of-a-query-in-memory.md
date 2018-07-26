---
title: Archiviare i risultati di una query in memoria
description: Come archiviare i risultati.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 52d502a841c428bd90a26c803ba577e76c17197c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404301"
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

[LINQ (Language-Integrated Query)](index.md)