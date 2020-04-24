---
title: Inserimento bulk
ms.date: 12/13/2019
description: Suggerimenti sulle prestazioni che è possibile utilizzare per apportare numerose modifiche al database.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447041"
---
# <a name="bulk-insert"></a>Inserimento bulk

SQLite non ha alcun modo speciale per eseguire l'inserimento bulk dei dati. Per ottenere prestazioni ottimali durante l'inserimento o l'aggiornamento dei dati, assicurarsi di eseguire le operazioni seguenti:

- Utilizzare una transazione.
- Riutilizzare lo stesso comando con parametri. Le esecuzioni successive riutilizzeranno la compilazione del primo.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
