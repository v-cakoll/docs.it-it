---
title: 'Guida di migrazione a .NET Framework 4.8, 4.7, 4.6 e 4.5 '
description: Guida per la migrazione a versioni di .NET Framework più recenti che includono risorse per le nuove funzionalità e la compatibilità delle applicazioni.
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
ms.openlocfilehash: a5b632824efacdb5e99228727b8751dc7f17d363
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86443416"
---
# <a name="migrate-to-net-framework-48-47-46-and-45"></a>Eseguire la migrazione a .NET Framework 4,8, 4,7, 4,6 e 4,5

Se l'app è stata creata usando una versione precedente di .NET Framework, in genere è possibile aggiornarla a .NET Framework 4,5 e alle relative versioni intermedie (4.5.1 e 4.5.2), .NET Framework 4,6 e le relative versioni intermedie (4.6.1 e 4.6.2), .NET Framework 4,7 e le relative versioni intermedie (4.7.1 e 4.7.2) o .NET Framework 4,8 con facilità. Aprire il progetto in Visual Studio. Se il progetto è stato creato in una versione precedente di Visual Studio, verrà visualizzata automaticamente la finestra di dialogo **Project Compatibility** (Compatibilità progetto). Per altre informazioni sull'aggiornamento di un progetto in Visual Studio, vedere [Conversione, migrazione e aggiornamento dei progetti di Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) e [Selezione della piattaforma e compatibilità di Visual Studio 2019](/visualstudio/releases/2019/compatibility).

 Tuttavia, alcune modifiche in .NET Framework richiedono modifiche al codice. È anche possibile che si voglia sfruttare le nuove funzionalità incluse in .NET Framework 4.5 e relative versioni intermedie, in .NET Framework 4.6 e relative versioni intermedie, in .NET Framework 4.7 e relative versioni intermedie e in NET Framework 4.8. L'esecuzione di questi tipi di modifiche nell'app per una nuova versione di .NET Framework viene in genere definita *migrazione*. Se non è necessario eseguire la migrazione dell'app, è possibile eseguirla in .NET Framework 4,5 o versione successiva senza ricompilarla.

## <a name="migration-resources"></a>Risorse per la migrazione

Prima di eseguire la migrazione dell'app da versioni precedenti di .NET Framework alla versione 4,5, 4.5.1, 4.5.2, 4,6, 4.6.1, 4.6.2, 4,7, 4.7.1, 4.7.2 o 4,8, vedere i documenti seguenti:

- Vedere [Versioni e dipendenze](versions-and-dependencies.md) per conoscere la versione CLR sottostante a ogni versione di .NET Framework e rivedere le linee guida per specificare le app come destinazione.

- Esaminare la [compatibilità delle applicazioni](application-compatibility.md) per ottenere informazioni sul runtime e sulle modifiche di reindirizzamento che potrebbero influire sull'app e su come gestirli.

- Consultare [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md) per determinare i tipi o i membri del codice resi obsoleti e le alternative consigliate.

- Vedere [Novità](../whats-new/index.md) per le descrizioni di nuove funzionalità che possono essere aggiunte all'app.

## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
- [Migrazione da .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Compatibilità delle versioni](version-compatibility.md)
- [Versioni e dipendenze](versions-and-dependencies.md)
- [Procedura: configurare un'app per supportare .NET Framework 4 o versioni successive](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Novità](../whats-new/index.md)
- [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md)
- [.NET Framework criteri di supporto ufficiale](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
- [Problemi di migrazione di .NET Framework 4](net-framework-4-migration-issues.md)
