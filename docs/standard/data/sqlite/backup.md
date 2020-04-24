---
title: Backup online
ms.date: 12/13/2019
description: Informazioni su come usare la funzionalità di backup online di SQLite.
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901280"
---
# <a name="online-backup"></a>Backup online

SQLite può eseguire il backup dei file di database durante l'esecuzione dell'app. Questa funzionalità è disponibile in Microsoft. Data. SQLite come <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> metodo in. `SqliteConnection`

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Attualmente, `BackupDatabase` eseguirà il backup del database il più rapidamente possibile e impedisce ad altre connessioni di scrivere nel database. Il problema [#13834](https://github.com/dotnet/efcore/issues/13834) fornirebbe un'API alternativa per eseguire il backup del database in background e consentire ad altre connessioni di interrompere il backup e scrivere nel database. Se si è interessati, fornire commenti e suggerimenti sul problema.
