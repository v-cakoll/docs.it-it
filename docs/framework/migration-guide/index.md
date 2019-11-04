---
title: 'Guida di migrazione a .NET Framework 4.8, 4.7, 4.6 e 4.5 '
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: 350d5400b4e1df7238702ce925c974eecb2a0d7a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457958"
---
# <a name="migration-guide-to-the-net-framework-48-47-46-and-45"></a>Guida di migrazione a .NET Framework 4.8, 4.7, 4.6 e 4.5

Se l'app è stata creata usando una versione precedente di .NET Framework, in genere è possibile aggiornarla con facilità a .NET Framework 4.5 e relative versioni intermedie (4.5.1 e 4.5.2), a .NET Framework 4.6 e relative versioni intermedie (4.6.1 e 4.6.2), a .NET Framework 4.7 e relative versioni intermedie (4.7.1 e 4.7.2) o a .NET Framework 4.8. Aprire il progetto in Visual Studio. Se il progetto è stato creato in una versione precedente di Visual Studio, verrà visualizzata automaticamente la finestra di dialogo **Project Compatibility** (Compatibilità progetto). Per altre informazioni sull'aggiornamento di un progetto in Visual Studio, vedere [Conversione, migrazione e aggiornamento dei progetti di Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) e [Selezione della piattaforma e compatibilità di Visual Studio 2019](/visualstudio/releases/2019/compatibility).

 Tuttavia, alcune modifiche in .NET Framework richiedono modifiche al codice. È anche possibile che si voglia sfruttare le nuove funzionalità incluse in .NET Framework 4.5 e relative versioni intermedie, in .NET Framework 4.6 e relative versioni intermedie, in .NET Framework 4.7 e relative versioni intermedie e in NET Framework 4.8. L'introduzione di questo tipo di modifiche in un'app per una nuova versione di .NET Framework viene in genere definita *migrazione*. Se non è necessario eseguire la migrazione dell'app, è possibile eseguirla in .NET Framework 4.5 o una versione successiva senza ricompilazione.

## <a name="migration-resources"></a>Risorse di migrazione

Esaminare i documenti seguenti prima di eseguire la migrazione dell'app da versioni precedenti di .NET Framework alla versione 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8:

- Vedere [Versioni e dipendenze](versions-and-dependencies.md) per conoscere la versione CLR sottostante a ogni versione di .NET Framework e rivedere le linee guida per specificare le app come destinazione.

- Esaminare la [compatibilità delle applicazioni](application-compatibility.md) per ottenere informazioni sul runtime e sulle modifiche di reindirizzamento che potrebbero influire sull'app e su come gestirli.

- Consultare [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md) per determinare i tipi o i membri del codice resi obsoleti e le alternative consigliate.

- Vedere [Novità](../whats-new/index.md) per le descrizioni di nuove funzionalità che possono essere aggiunte all'app.

## <a name="see-also"></a>Vedere anche

- [Compatibilità delle applicazioni](application-compatibility.md)
- [Migrazione da .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Compatibilità tra versioni](version-compatibility.md)
- [Versioni e dipendenze](versions-and-dependencies.md)
- [Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Novità](../whats-new/index.md)
- [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md)
- [.NET Framework Version and Assembly Information (Informazioni su assembly e versioni di .NET Framework)](https://go.microsoft.com/fwlink/?LinkId=201701)
- [Criteri relativi al ciclo di vita del supporto di Microsoft .NET Framework](https://go.microsoft.com/fwlink/?LinkId=196607)
- [Problemi di migrazione di .NET Framework 4](net-framework-4-migration-issues.md)
