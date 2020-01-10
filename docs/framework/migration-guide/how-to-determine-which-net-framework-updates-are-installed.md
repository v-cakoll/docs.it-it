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
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="119ee-103">Come determinare quali aggiornamenti di sicurezza e hotfix di .NET Framework sono installati</span><span class="sxs-lookup"><span data-stu-id="119ee-103">How to determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="119ee-104">Questo articolo illustra come trovare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer.</span><span class="sxs-lookup"><span data-stu-id="119ee-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="119ee-105">Tutte le tecniche illustrate in questo articolo richiedono un account con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="119ee-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="use-registry-editor"></a><span data-ttu-id="119ee-106">Utilizzare l'editor del registro di sistema</span><span class="sxs-lookup"><span data-stu-id="119ee-106">Use Registry Editor</span></span>

<span data-ttu-id="119ee-107">Gli aggiornamenti della sicurezza e gli aggiornamenti rapidi installati per ogni versione di .NET Framework installata in un computer sono elencati nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="119ee-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="119ee-108">Per visualizzare queste informazioni, è possibile usare il programma Editor del Registro di sistema (*regedit.exe*).</span><span class="sxs-lookup"><span data-stu-id="119ee-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="119ee-109">Aprire il programma **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="119ee-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="119ee-110">In Windows 8 e versioni successive, fare clic con il pulsante destro del mouse su **Start** ![screenshot del logo della chiave Windows](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="119ee-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="119ee-111">Nella casella **Apri** immettere **regedit** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="119ee-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="119ee-112">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="119ee-112">In the Registry Editor, open the following subkey:</span></span>

     <span data-ttu-id="119ee-113">**HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\Updates**</span><span class="sxs-lookup"><span data-stu-id="119ee-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span></span>

     <span data-ttu-id="119ee-114">Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano.</span><span class="sxs-lookup"><span data-stu-id="119ee-114">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="119ee-115">Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="119ee-115">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="119ee-116">Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse.</span><span class="sxs-lookup"><span data-stu-id="119ee-116">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="119ee-117">Per informazioni sul rilevamento dei numeri delle versioni installate, vedere [Procedura: Determinare le versioni di .NET Framework installate](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="119ee-117">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="query-the-registry-using-code"></a><span data-ttu-id="119ee-118">Eseguire query sul Registro di sistema usando il codice</span><span class="sxs-lookup"><span data-stu-id="119ee-118">Query the registry using code</span></span>

<span data-ttu-id="119ee-119">L'esempio seguente consente di determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer a livello di codice:</span><span class="sxs-lookup"><span data-stu-id="119ee-119">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="119ee-120">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="119ee-120">The example produces an output that's similar to the following one:</span></span>

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

## <a name="use-powershell-to-query-the-registry"></a><span data-ttu-id="119ee-121">Usare PowerShell per eseguire query sul Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="119ee-121">Use PowerShell to query the registry</span></span>

<span data-ttu-id="119ee-122">L'esempio seguente illustra come determinare gli aggiornamenti della sicurezza e gli aggiornamenti rapidi di .NET Framework installati in un computer usando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="119ee-122">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

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

<span data-ttu-id="119ee-123">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="119ee-123">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="119ee-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="119ee-124">See also</span></span>

- [<span data-ttu-id="119ee-125">Procedura: Determinare le versioni di .NET Framework installate</span><span class="sxs-lookup"><span data-stu-id="119ee-125">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="119ee-126">Installare .NET Framework per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="119ee-126">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="119ee-127">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="119ee-127">Versions and dependencies</span></span>](versions-and-dependencies.md)
