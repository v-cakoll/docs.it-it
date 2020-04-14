---
title: Estensioni
ms.date: 12/13/2019
description: Scopri come caricare le estensioni SQLite.
ms.openlocfilehash: 51c705349c25240fe42e0edda8004a3e3b013ca3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242959"
---
# <a name="extensions"></a>Estensioni

SQLite supporta il caricamento delle estensioni in fase di esecuzione. Le estensioni includono elementi come funzioni SQL aggiuntive, regole di confronto, tabelle virtuali e altro ancora.

.NET Core include logica aggiuntiva per l'individuazione di librerie native in posizioni aggiuntive, ad esempio pacchetti NuGet di riferimento. Sfortunatamente, SQLite non può sfruttare questa logica; chiama direttamente l'API della piattaforma per caricare le librerie. Per questo motivo, potrebbe essere necessario modificare le variabili di ambiente PATH, LD_LIBRARY_PATH o DYLD_LIBRARY_PATH prima di caricare le estensioni SQLite. C'è [un esempio](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs) su GitHub che illustra la ricerca di binari per il runtime corrente all'interno di un pacchetto NuGet di riferimento.

Per caricare un'estensione, chiamare il <xref:Microsoft.Data.Sqlite.SqliteConnection.LoadExtension%2A> metodo . Microsoft.Data.Sqlite garantirà che l'estensione rimanga caricata anche se la connessione viene chiusa e riaperta.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ExtensionsSample/Program.cs?name=snippet_LoadExtension)]

## <a name="see-also"></a>Vedere anche

* [Estensioni caricabili in fase di esecuzioneRun-Time Loadable Extensions](https://www.sqlite.org/loadext.html)
