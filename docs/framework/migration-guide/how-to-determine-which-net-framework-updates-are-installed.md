---
title: 'Procedura: Determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati'
description: Informazioni su come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.
ms.date: 11/27/2017
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
ms.openlocfilehash: 9ff10928b87834f9b8e74e269082919f49497023
ms.sourcegitcommit: 39b65a49271e082add68cb737b48fdbe09d24718
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>Procedura: Determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati

Questo articolo illustra come trovare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.

> [!NOTE]
> Tutte le tecniche illustrate in questo articolo richiedono un account con privilegi amministrativi.

## <a name="to-find-installed-updates-using-the-registry"></a>Per trovare gli aggiornamenti installati usando il Registro di sistema

Gli aggiornamenti della sicurezza e gli aggiornamenti rapidi installati per ogni versione di .NET Framework installata in un computer sono elencati nel Registro di sistema di Windows. Per visualizzare queste informazioni, è possibile usare il programma Editor del Registro di sistema (*regedit.exe*).

1. Aprire il programma **regedit.exe**. In Windows 8 e versioni successive fare clic con il pulsante destro del mouse su **Start** ![Logo di Windows](../get-started/media/windowskeyboardlogo.png "tasto WINDOWS"), quindi scegliere **Esegui**. Nella casella **Apri** immettere **regedit** e fare clic su **OK**.

2. Nell'Editor del Registro di sistema aprire la seguente sottochiave:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano. Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).

Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse. Per informazioni sul rilevamento dei numeri delle versioni installate, vedere [Procedura: Determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>Per trovare gli aggiornamenti installati eseguendo una query sul Registro di sistema nel codice

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>Per trovare gli aggiornamenti installati eseguendo una query sul Registro di sistema in PowerShell

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

[Procedura: Determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[Installare .NET Framework per sviluppatori](../../../docs/framework/install/guide-for-developers.md)  
[Versioni e dipendenze](../../../docs/framework/migration-guide/versions-and-dependencies.md)
