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
# <a name="online-backup"></a><span data-ttu-id="1248a-103">Backup online.</span><span class="sxs-lookup"><span data-stu-id="1248a-103">Online backup</span></span>

<span data-ttu-id="1248a-104">SQLite può eseguire il backup dei file di database durante l'esecuzione dell'app.</span><span class="sxs-lookup"><span data-stu-id="1248a-104">SQLite can back up database files while the app is running.</span></span> <span data-ttu-id="1248a-105">Questa funzionalità è disponibile in Microsoft. Data. SQLite come metodo di <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> in `SqliteConnection`.</span><span class="sxs-lookup"><span data-stu-id="1248a-105">This functionality is available in Microsoft.Data.Sqlite as the <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> method on `SqliteConnection`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

<span data-ttu-id="1248a-106">Attualmente, `BackupDatabase` eseguirà il backup del database il più rapidamente possibile e blocca le altre connessioni dalla scrittura al database.</span><span class="sxs-lookup"><span data-stu-id="1248a-106">Currently, `BackupDatabase` will back up the database as quickly as possible and blocks other connections from writing to the database.</span></span> <span data-ttu-id="1248a-107">Il problema [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) fornirebbe un'API alternativa per eseguire il backup del database in background e consentire ad altre connessioni di interrompere il backup e scrivere nel database.</span><span class="sxs-lookup"><span data-stu-id="1248a-107">Issue [#13834](https://github.com/aspnet/EntityFrameworkCore/issues/13834) would provide an alternative API to back up the database in the background and allow other connections to interrupt the backup and write to the database.</span></span> <span data-ttu-id="1248a-108">Se si è interessati, fornire commenti e suggerimenti sul problema.</span><span class="sxs-lookup"><span data-stu-id="1248a-108">If you're interested, provide feedback on the issue.</span></span>
