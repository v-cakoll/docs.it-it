---
title: Vedere installato .NET Framework aggiornamenti della sicurezza e hotfix
description: Informazioni su come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 087519048b412798ef7495d250dc2538ee5c2fd0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716262"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Come determinare quali aggiornamenti di sicurezza e hotfix di .NET Framework sono installati

Questo articolo illustra come trovare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.

> [!NOTE]
> Tutte le tecniche illustrate in questo articolo richiedono un account con privilegi amministrativi.

## <a name="use-registry-editor"></a>Utilizzare l'editor del registro di sistema

Gli aggiornamenti della sicurezza e gli aggiornamenti rapidi installati per ogni versione di .NET Framework installata in un computer sono elencati nel Registro di sistema di Windows. Per visualizzare queste informazioni, è possibile usare il programma Editor del Registro di sistema (*regedit.exe*).

1. Aprire il programma **regedit.exe**. In Windows 8 e versioni successive, fare clic con il pulsante destro del mouse su **Start** ![screenshot del logo della chiave Windows](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), quindi scegliere **Esegui**. Nella casella **Apri** immettere **regedit** e fare clic su **OK**.

2. Nell'Editor del Registro di sistema aprire la seguente sottochiave:

     **HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\Updates**

     Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano. Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).

Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse. Per informazioni sul rilevamento dei numeri delle versioni installate, vedere [Procedura: Determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md).

## <a name="query-the-registry-using-code"></a>Eseguire query sul Registro di sistema usando il codice

L'esempio seguente consente di determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer a livello di codice:

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

In questo esempio viene generato un output simile al seguente:

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

## <a name="use-powershell-to-query-the-registry"></a>Usare PowerShell per eseguire query sul Registro di sistema

L'esempio seguente illustra come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer usando PowerShell:

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

In questo esempio viene generato un output simile al seguente:

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

## <a name="see-also"></a>Vedere anche

- [Procedura: Determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md)
- [Installare .NET Framework per sviluppatori](../install/guide-for-developers.md)
- [Versioni e dipendenze](versions-and-dependencies.md)
