---
title: 'Procedura: Determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati'
description: Informazioni su come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c69d4bb370087dddafbfed41cbfb1fef229677c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318963"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="9ca85-103">Procedura: Determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati</span><span class="sxs-lookup"><span data-stu-id="9ca85-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="9ca85-104">Questo articolo illustra come trovare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.</span><span class="sxs-lookup"><span data-stu-id="9ca85-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca85-105">Tutte le tecniche illustrate in questo articolo richiedono un account con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="9ca85-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="9ca85-106">Per trovare gli aggiornamenti installati usando il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9ca85-106">To find installed updates using the registry</span></span>

<span data-ttu-id="9ca85-107">Gli aggiornamenti della sicurezza e gli aggiornamenti rapidi installati per ogni versione di .NET Framework installata in un computer sono elencati nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="9ca85-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="9ca85-108">Per visualizzare queste informazioni, è possibile usare il programma Editor del Registro di sistema (*regedit.exe*).</span><span class="sxs-lookup"><span data-stu-id="9ca85-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="9ca85-109">Aprire il programma **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="9ca85-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="9ca85-110">In Windows 8 e versioni successive, fare clic con il pulsante destro del mouse su **Start** ![screenshot del logo della chiave Windows.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), quindi selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9ca85-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="9ca85-111">Nella casella **Apri** immettere **regedit** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ca85-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="9ca85-112">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="9ca85-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="9ca85-113">Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano.</span><span class="sxs-lookup"><span data-stu-id="9ca85-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="9ca85-114">Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="9ca85-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="9ca85-115">Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse.</span><span class="sxs-lookup"><span data-stu-id="9ca85-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="9ca85-116">Per informazioni sul rilevamento dei numeri delle versioni installate, vedere [Procedura: Determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="9ca85-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="9ca85-117">Per trovare gli aggiornamenti installati eseguendo una query sul Registro di sistema nel codice</span><span class="sxs-lookup"><span data-stu-id="9ca85-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="9ca85-118">L'esempio seguente consente di determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer a livello di codice:</span><span class="sxs-lookup"><span data-stu-id="9ca85-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="9ca85-119">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9ca85-119">The example produces an output that's similar to the following one:</span></span>

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="9ca85-120">Per trovare gli aggiornamenti installati eseguendo una query sul Registro di sistema in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca85-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="9ca85-121">L'esempio seguente illustra come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer usando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ca85-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="9ca85-122">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9ca85-122">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9ca85-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ca85-123">See also</span></span>

- [<span data-ttu-id="9ca85-124">Procedura: Determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="9ca85-124">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="9ca85-125">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="9ca85-125">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="9ca85-126">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="9ca85-126">Versions and dependencies</span></span>](versions-and-dependencies.md)
