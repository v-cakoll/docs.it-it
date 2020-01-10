---
title: Estensioni di
ms.date: 12/13/2019
description: Informazioni su come caricare le estensioni SQLite.
ms.openlocfilehash: 74b207205492bac48c89cb756470326f8e4a13c4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777378"
---
# <a name="extensions"></a>Estensioni di

SQLite supporta il caricamento delle estensioni in fase di esecuzione. Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.

.NET Core include una logica aggiuntiva per l'individuazione delle librerie native in altre posizioni, come i pacchetti NuGet a cui si fa riferimento. Sfortunatamente, SQLite non può sfruttare questa logica. chiama direttamente l'API della piattaforma per caricare le librerie. Per questo motivo, è possibile che l'app debba modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite. In GitHub è disponibile [un esempio](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) che illustra come trovare i file binari per il runtime corrente all'interno di un pacchetto NuGet a cui si fa riferimento.

Per caricare un'estensione, chiamare il metodo <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A>. Microsoft. Data. sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vedere anche

* [Estensioni caricabili in fase di esecuzione](https://www.sqlite.org/loadext.html)
