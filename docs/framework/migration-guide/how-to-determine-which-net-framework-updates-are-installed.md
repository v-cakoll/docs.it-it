---
title: 'Procedura: determinare gli aggiornamenti di .NET Framework installati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: 6
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b29b402e859688dcced6bd4429b18298070fb5e4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a><span data-ttu-id="bf854-102">Procedura: determinare gli aggiornamenti di .NET Framework installati</span><span class="sxs-lookup"><span data-stu-id="bf854-102">How to: Determine Which .NET Framework Updates Are Installed</span></span>
<span data-ttu-id="bf854-103">Gli aggiornamenti installati per ogni versione di .NET Framework installata in un computer sono elencati nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="bf854-103">The installed updates for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="bf854-104">Per visualizzare queste informazioni, è possibile usare l'Editor del Registro di sistema (regedit.exe).</span><span class="sxs-lookup"><span data-stu-id="bf854-104">You can use the Registry Editor (regedit.exe) to view this information.</span></span>  
  
 <span data-ttu-id="bf854-105">Nell'Editor del Registro di sistema le versioni di .NET Framework e gli aggiornamenti installati per ogni versione sono archiviati in sottochiavi diverse.</span><span class="sxs-lookup"><span data-stu-id="bf854-105">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="bf854-106">Per informazioni sul rilevamento dei numeri delle versioni installate, vedere [Procedura: determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="bf854-106">For information about detecting the installed version numbers, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span> <span data-ttu-id="bf854-107">Per informazioni sull'installazione di .NET Framework, vedere [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="bf854-107">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
### <a name="to-find-installed-updates"></a><span data-ttu-id="bf854-108">Per individuare gli aggiornamenti installati</span><span class="sxs-lookup"><span data-stu-id="bf854-108">To find installed updates</span></span>  
  
1.  <span data-ttu-id="bf854-109">Aprire il programma **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="bf854-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="bf854-110">In Windows 8 e versioni successive aprire la schermata Start e digitare il nome.</span><span class="sxs-lookup"><span data-stu-id="bf854-110">In Windows 8 and higher open the Start screen and type the name.</span></span> <span data-ttu-id="bf854-111">Nelle versioni precedenti di Windows, fare clic sul pulsante **Start** per aprire il relativo menu, scegliere **Esegui** e nella casella **Apri** immettere **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="bf854-111">In earlier versions of Windows, on the **Start** menu, choose **Run** and then, in the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="bf854-112">Per eseguire regedit.exe, è necessario disporre di privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="bf854-112">You must have administrative credentials to run regedit.exe.</span></span>  
  
2.  <span data-ttu-id="bf854-113">Nell'Editor del Registro di sistema aprire la seguente sottochiave:</span><span class="sxs-lookup"><span data-stu-id="bf854-113">In the Registry Editor, open the following subkey:</span></span>  
  
     <span data-ttu-id="bf854-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span><span class="sxs-lookup"><span data-stu-id="bf854-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span></span>  
  
     <span data-ttu-id="bf854-115">Gli aggiornamenti installati sono elencati nelle sottochiavi che identificano la versione di .NET Framework a che si applicano.</span><span class="sxs-lookup"><span data-stu-id="bf854-115">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="bf854-116">Ogni aggiornamento è identificato da un numero di Knowledge Base (KB).</span><span class="sxs-lookup"><span data-stu-id="bf854-116">Each update is identified by a Knowledge Base (KB) number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf854-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf854-117">Example</span></span>  
 <span data-ttu-id="bf854-118">Il codice seguente consente di determinare gli aggiornamenti di .NET Framework installati in un computer a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="bf854-118">The following code programmatically determines the .NET Framework updates that are installed on a computer.</span></span> <span data-ttu-id="bf854-119">Per eseguire questo esempio, è necessario disporre delle credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="bf854-119">You must have administrative credentials to run this example.</span></span>  
  
 <span data-ttu-id="bf854-120">[!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)] [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="bf854-120">[!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)] [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]</span></span>  
  
 <span data-ttu-id="bf854-121">In questo esempio viene generato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="bf854-121">The example produces output that's similar to the following:</span></span>  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf854-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf854-122">See also</span></span>

<span data-ttu-id="bf854-123">[Procedura: determinare le versioni di .NET Framework installate](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="bf854-123">[How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span></span>  
<span data-ttu-id="bf854-124">[Installare .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="bf854-124">[Installing the .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span></span>  
[<span data-ttu-id="bf854-125">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="bf854-125">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)

