---
title: 'Procedura: determinare quali aggiornamenti di sicurezza di .NET Framework e gli hotfix installati'
description: Informazioni su come determinare quali aggiornamenti di sicurezza di .NET Framework e gli hotfix vengono installati in un computer.
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Procedura: determinare quali aggiornamenti di sicurezza di .NET Framework e gli hotfix installati

Questo articolo illustra come determinare quali aggiornamenti di .NET Framework e gli hotfix vengono installati in un computer.

> [!NOTE]
> Tutte le tecniche illustrate in questo articolo è necessario un account con privilegi amministrativi.

## <a name="to-find-installed-updates-using-the-registry"></a>Per individuare gli aggiornamenti installati tramite il Registro di sistema

Gli installati gli aggiornamenti e hotfix per ogni versione di .NET Framework installato in un computer sono elencati nel Registro di sistema Windows. È possibile utilizzare l'Editor del Registro di sistema (*regedit.exe*) programma per visualizzare queste informazioni.

1. Aprire il programma **regedit.exe**. In Windows 8 e versioni successive, fare doppio clic su **avviare** ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), quindi selezionare **eseguire**. Nel **aprire** immettere **regedit** e selezionare **OK**.

2. Nell'Editor del Registro di sistema aprire la seguente sottochiave:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano. Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).

Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse. Per informazioni sul rilevamento dei numeri di versione, vedere [procedura: determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Per trovare aggiornamenti installati esaminando il Registro di sistema nel codice

Nell'esempio seguente viene determinato a livello di programmazione di aggiornamenti di sicurezza di .NET Framework e gli aggiornamenti rapidi installati in un computer:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

Questo esempio produce un output simile a quello riportato di seguito:

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Per trovare aggiornamenti installati eseguendo una query nel Registro di sistema di PowerShell

Nell'esempio seguente viene illustrato come determinare il aggiornamenti di sicurezza di .NET Framework e gli aggiornamenti rapidi installati in un computer con PowerShell:

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

Questo esempio produce un output simile a quello riportato di seguito:

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>Vedere anche

[Procedura: determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Installare .NET Framework per sviluppatori](../../../docs/framework/install/guide-for-developers.md)  
[Versioni e dipendenze](../../../docs/framework/migration-guide/versions-and-dependencies.md)
