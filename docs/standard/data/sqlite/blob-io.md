---
title: I/O BLOB
ms.date: 12/13/2019
description: Informazioni su come usare la funzionalità di I/O BLOB di SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447048"
---
# <a name="blob-io"></a>I/O BLOB

Per ridurre l'utilizzo della memoria durante la lettura e la scrittura di oggetti di grandi dimensioni, è possibile trasmettere i dati all'interno e all'esterno del database. Questo può essere particolarmente utile quando si analizzano o si trasformano i dati.

Per iniziare, inserire una riga come normale. Utilizzare la `zeroblob()` funzione SQL per allocare spazio nel database in modo che contenga l'oggetto di grandi dimensioni. La `last_insert_rowid()` funzione fornisce un modo pratico per ottenere il proprio ROWID.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

Dopo aver inserito la riga, aprire un flusso per scrivere l'oggetto di grandi <xref:Microsoft.Data.Sqlite.SqliteBlob>dimensioni utilizzando.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Per trasmettere l'oggetto di grandi dimensioni all'esterno del database, è necessario selezionare il ROWID o uno dei relativi alias, come illustrato qui, oltre alla colonna dell'oggetto large. Se non si seleziona ROWID, l'intero oggetto verrà caricato in memoria. Quando viene eseguita correttamente `GetStream()` , l'oggetto restituito da sarà. `SqliteBlob`

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
