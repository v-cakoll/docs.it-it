---
title: inserimento di massa
ms.date: 12/13/2019
description: Suggerimenti sulle prestazioni che è possibile utilizzare per apportare numerose modifiche al database.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447041"
---
# <a name="bulk-insert"></a><span data-ttu-id="d0401-103">inserimento di massa</span><span class="sxs-lookup"><span data-stu-id="d0401-103">Bulk insert</span></span>

<span data-ttu-id="d0401-104">SQLite non ha alcun modo speciale per eseguire l'inserimento bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="d0401-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="d0401-105">Per ottenere prestazioni ottimali durante l'inserimento o l'aggiornamento dei dati, assicurarsi di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0401-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="d0401-106">Utilizzare una transazione.</span><span class="sxs-lookup"><span data-stu-id="d0401-106">Use a transaction.</span></span>
- <span data-ttu-id="d0401-107">Riutilizzare lo stesso comando con parametri.</span><span class="sxs-lookup"><span data-stu-id="d0401-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="d0401-108">Le esecuzioni successive riutilizzeranno la compilazione del primo.</span><span class="sxs-lookup"><span data-stu-id="d0401-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
