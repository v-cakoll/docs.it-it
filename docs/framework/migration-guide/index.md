---
title: 'Guida di migrazione a .NET Framework 4.7, 4.6 e 4.5 '
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 59c4ae2961b3e029ddd5f67afc9644042af95efb
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a>Guida di migrazione a .NET Framework 4.7, 4.6 e 4.5 
Se un'app è stata creata usando una versione precedente di .NET Framework, in genere è possibile aggiornarla facilmente a .NET Framework 4.5 e alle relative versioni intermedie (4.5.1 e 4.5.2), a .NET Framework 4.6 e alle relative versioni intermedie (4.6.1 e 4.6.2) o a .NET Framework 4.7 e alla relativa versione intermedia, .NET Framework 4.7.1. Aprire il progetto in Visual Studio. Se il progetto è stato creato in una versione precedente di Visual Studio, verrà visualizzata automaticamente la finestra di dialogo **Project Compatibility** (Compatibilità progetto). Per altre informazioni sull'aggiornamento di un progetto in Visual Studio, vedere [Conversione, migrazione e aggiornamento dei progetti di Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) e [Selezione della piattaforma e compatibilità di Visual Studio 2017](/visualstudio/productinfo/vs2017-compatibility-vs).  
  
 Tuttavia, alcune modifiche in .NET Framework richiedono modifiche al codice. È anche possibile che si voglia sfruttare le nuove funzionalità incluse in .NET Framework 4.5 e nelle relative versioni intermedie, in .NET Framework 4.6 e nelle relative versioni intermedie o in .NET Framework 4.7 e nella relativa versione intermedia, .NET Framework 4.7.1. L'introduzione di questo tipo di modifiche in un'app per una nuova versione di .NET Framework viene in genere definita *migrazione*. Se non è necessario eseguire la migrazione dell'app, è possibile eseguirla in .NET Framework 4.5 o una versione successiva senza ricompilazione.  
  
## <a name="migration-resources"></a>Risorse di migrazione  
 Esaminare i documenti seguenti prima di eseguire la migrazione dell'app da versioni precedenti di .NET Framework alla versione 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 o 4.7.1:  
  
-   Vedere [Versioni e dipendenze](../../../docs/framework/migration-guide/versions-and-dependencies.md) per conoscere la versione CLR sottostante a ogni versione di .NET Framework e rivedere le linee guida per specificare le app come destinazione.  
  
-   Consultare [Compatibilità delle applicazioni](../../../docs/framework/migration-guide/application-compatibility.md) per ottenere informazioni sul runtime e sulle modifiche di reindirizzamento che potrebbero interessare l'app e su come gestirle.  
  
-   Consultare [Elementi obsoleti nella libreria di classi](../../../docs/framework/whats-new/whats-obsolete.md) per determinare i tipi o i membri del codice resi obsoleti e le alternative consigliate.  
  
-   Vedere [Novità](../../../docs/framework/whats-new/index.md) per le descrizioni di nuove funzionalità che possono essere aggiunte all'app.  
  
## <a name="see-also"></a>Vedere anche  
 [Compatibilità delle applicazioni](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Migrazione da .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [Compatibilità tra versioni](../../../docs/framework/migration-guide/version-compatibility.md)  
 [Versioni e dipendenze](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [Procedura: Configurare un'app per supportare .NET Framework 4 o 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [Novità](../../../docs/framework/whats-new/index.md)  
 [Elementi obsoleti nella libreria di classi](../../../docs/framework/whats-new/whats-obsolete.md)  
 [.NET Framework Version and Assembly Information (Informazioni su assembly e versioni di .NET Framework)](http://go.microsoft.com/fwlink/?LinkId=201701)  
 [Criteri relativi al ciclo di vita del supporto di Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=196607) [Problemi di migrazione di .NET Framework 4](net-framework-4-migration-issues.md)
