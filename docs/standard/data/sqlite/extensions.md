---
title: Estensioni
ms.date: 12/13/2019
description: Informazioni su come caricare le estensioni SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242959"
---
# <a name="extensions"></a>Estensioni

SQLite supporta il caricamento delle estensioni in fase di esecuzione. Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.

.NET Core include una logica aggiuntiva per l'individuazione delle librerie native in altre posizioni, come i pacchetti NuGet a cui si fa riferimento. Sfortunatamente, SQLite non può sfruttare questa logica. chiama direttamente l'API della piattaforma per caricare le librerie. Per questo motivo, potrebbe essere necessario modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite. In GitHub è disponibile [un esempio](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) che illustra come trovare i file binari per il runtime corrente all'interno di un pacchetto NuGet a cui si fa riferimento.

Per caricare un'estensione, chiamare il <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> metodo. Microsoft. Data. sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vedi anche

* [Estensioni caricabili in fase di esecuzione](https://www.sqlite.org/loadext.html)
