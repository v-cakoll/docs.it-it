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
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="89889-103">Procedura: determinare quali aggiornamenti di sicurezza di .NET Framework e gli hotfix installati</span><span class="sxs-lookup"><span data-stu-id="89889-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="89889-104">Questo articolo illustra come determinare quali aggiornamenti di .NET Framework e gli hotfix vengono installati in un computer.</span><span class="sxs-lookup"><span data-stu-id="89889-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="89889-105">Tutte le tecniche illustrate in questo articolo è necessario un account con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="89889-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="89889-106">Per individuare gli aggiornamenti installati tramite il Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="89889-106">To find installed updates using the registry</span></span>

<span data-ttu-id="89889-107">Gli installati gli aggiornamenti e hotfix per ogni versione di .NET Framework installato in un computer sono elencati nel Registro di sistema Windows.</span><span class="sxs-lookup"><span data-stu-id="89889-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="89889-108">È possibile utilizzare l'Editor del Registro di sistema (*regedit.exe*) programma per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="89889-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="89889-109">Aprire il programma **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="89889-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="89889-110">In Windows 8 e versioni successive, fare doppio clic su **avviare** ![logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), quindi selezionare **eseguire**.</span><span class="sxs-lookup"><span data-stu-id="89889-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="89889-111">Nel **aprire** immettere **regedit** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="89889-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="89889-112">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="89889-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="89889-113">Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano.</span><span class="sxs-lookup"><span data-stu-id="89889-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="89889-114">Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="89889-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="89889-115">Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse.</span><span class="sxs-lookup"><span data-stu-id="89889-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="89889-116">Per informazioni sul rilevamento dei numeri di versione, vedere [procedura: determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="89889-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="89889-117">Per trovare aggiornamenti installati esaminando il Registro di sistema nel codice</span><span class="sxs-lookup"><span data-stu-id="89889-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="89889-118">Nell'esempio seguente viene determinato a livello di programmazione di aggiornamenti di sicurezza di .NET Framework e gli aggiornamenti rapidi installati in un computer:</span><span class="sxs-lookup"><span data-stu-id="89889-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="89889-119">Questo esempio produce un output simile a quello riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="89889-119">The example produces an output that's similar to the following one:</span></span>

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

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="89889-120">Per trovare aggiornamenti installati eseguendo una query nel Registro di sistema di PowerShell</span><span class="sxs-lookup"><span data-stu-id="89889-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="89889-121">Nell'esempio seguente viene illustrato come determinare il aggiornamenti di sicurezza di .NET Framework e gli aggiornamenti rapidi installati in un computer con PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89889-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

<span data-ttu-id="89889-122">Questo esempio produce un output simile a quello riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="89889-122">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="89889-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89889-123">See also</span></span>

[<span data-ttu-id="89889-124">Procedura: determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="89889-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="89889-125">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="89889-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="89889-126">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="89889-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
