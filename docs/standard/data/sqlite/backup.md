---
title: Backup online.
ms.date: 12/13/2019
description: Informazioni su come usare la funzionalità di backup online di SQLite.
ms.openlocfilehash: 885aa2c5555b58deb2551c0a4e6933742a093457
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447097"
---
# <a name="online-backup"></a>Backup online.

SQLite può eseguire il backup dei file di database durante l'esecuzione dell'app. Questa funzionalità è disponibile in Microsoft. Data. SQLite come metodo di <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> in `SqliteConnection`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

Attualmente, `BackupDatabase` eseguirà il backup del database il più rapidamente possibile e blocca le altre connessioni dalla scrittura al database. Il problema [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) fornirebbe un'API alternativa per eseguire il backup del database in background e consentire ad altre connessioni di interrompere il backup e scrivere nel database. Se si è interessati, fornire commenti e suggerimenti sul problema.
