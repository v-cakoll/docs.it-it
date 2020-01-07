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
# <a name="interoperability"></a>Interoperabilità

Microsoft. Data. sqlite USA SQLitePCLRaw per interagire con la libreria SQLite nativa. SQLitePCLRaw fornisce un'API .NET Thin sull'API SQLite nativa. SqliteConnection e SqliteDataReader consentono di accedere agli oggetti SQLitePCLRaw sottostanti consentendo di chiamare direttamente queste API.

Nell'esempio seguente viene illustrato come chiamare `sqlite3_trace` per scrivere istruzioni SQL eseguite nella console:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_Trace)]

Nell'esempio seguente viene illustrata la chiamata di `sqlite3_stmt_status` per vedere il numero di passaggi della macchina virtuale SQLite di un'istruzione SQL compilata in:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

Gli oggetti SQLitePCLRaw espongono anche un puntatore agli oggetti nativi che consentono di P/Invoke altre API SQLite native.
