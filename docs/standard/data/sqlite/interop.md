---
title: Interoperabilità
ms.date: 12/13/2019
description: Informazioni su come interagire con altre librerie SQLite.
ms.openlocfilehash: 486e2a8e00999b8ebe9c85a5fcc1539c514676d3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447237"
---
# <a name="interoperability"></a><span data-ttu-id="a2136-103">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a2136-103">Interoperability</span></span>

<span data-ttu-id="a2136-104">Microsoft. Data. sqlite USA SQLitePCLRaw per interagire con la libreria SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="a2136-104">Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library.</span></span> <span data-ttu-id="a2136-105">SQLitePCLRaw fornisce un'API .NET Thin sull'API SQLite nativa.</span><span class="sxs-lookup"><span data-stu-id="a2136-105">SQLitePCLRaw provides a thin .NET API over the native SQLite API.</span></span> <span data-ttu-id="a2136-106">SqliteConnection e SqliteDataReader consentono di accedere agli oggetti SQLitePCLRaw sottostanti consentendo di chiamare direttamente queste API.</span><span class="sxs-lookup"><span data-stu-id="a2136-106">SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.</span></span>

<span data-ttu-id="a2136-107">Nell'esempio seguente viene illustrato come chiamare `sqlite3_trace` per scrivere istruzioni SQL eseguite nella console:</span><span class="sxs-lookup"><span data-stu-id="a2136-107">The following example shows how to call `sqlite3_trace` to write executed SQL statements to the console:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

<span data-ttu-id="a2136-108">Nell'esempio seguente viene illustrata la chiamata di `sqlite3_stmt_status` per vedere il numero di passaggi della macchina virtuale SQLite di un'istruzione SQL compilata in:</span><span class="sxs-lookup"><span data-stu-id="a2136-108">And the following example shows calling `sqlite3_stmt_status` to see how many SQLite virtual machine steps a SQL statement compiled into:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

<span data-ttu-id="a2136-109">Gli oggetti SQLitePCLRaw espongono anche un puntatore agli oggetti nativi che consentono di P/Invoke altre API SQLite native.</span><span class="sxs-lookup"><span data-stu-id="a2136-109">The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.</span></span>
