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
# <a name="blob-io"></a><span data-ttu-id="ef1ee-103">I/O BLOB</span><span class="sxs-lookup"><span data-stu-id="ef1ee-103">Blob I/O</span></span>

<span data-ttu-id="ef1ee-104">Per ridurre l'utilizzo della memoria durante la lettura e la scrittura di oggetti di grandi dimensioni, è possibile trasmettere i dati all'interno e all'esterno del database.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="ef1ee-105">Questo può essere particolarmente utile quando si analizzano o si trasformano i dati.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="ef1ee-106">Per iniziare, inserire una riga come normale.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="ef1ee-107">Utilizzare la funzione SQL `zeroblob()` per allocare spazio nel database in modo che contenga l'oggetto di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="ef1ee-108">La funzione `last_insert_rowid()` rappresenta un modo pratico per ottenere il proprio ROWID.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="ef1ee-109">Dopo aver inserito la riga, aprire un flusso per scrivere l'oggetto di grandi dimensioni utilizzando <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="ef1ee-110">Per trasmettere l'oggetto di grandi dimensioni all'esterno del database, è necessario selezionare il ROWID o uno dei relativi alias, come illustrato qui, oltre alla colonna dell'oggetto large.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="ef1ee-111">Se non si seleziona ROWID, l'intero oggetto verrà caricato in memoria.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="ef1ee-112">L'oggetto restituito da `GetStream()` sarà una `SqliteBlob` se eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef1ee-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
