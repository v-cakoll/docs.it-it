---
title: Storeadm.exe (strumento per lo spazio di memorizzazione isolato)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c9b8d0680a50d9945bef0d03d10e45750fc49a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410267"
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="5350f-102">Storeadm.exe (strumento per lo spazio di memorizzazione isolato)</span><span class="sxs-lookup"><span data-stu-id="5350f-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="5350f-103">Lo strumento per lo spazio di memorizzazione isolato elenca o rimuove tutti gli archivi esistenti dell'utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="5350f-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="5350f-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5350f-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="5350f-105">Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5350f-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="5350f-106">Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="5350f-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="5350f-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5350f-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5350f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5350f-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5350f-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="5350f-109">Parameters</span></span>  
  
|<span data-ttu-id="5350f-110">Opzione</span><span class="sxs-lookup"><span data-stu-id="5350f-110">Option</span></span>|<span data-ttu-id="5350f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5350f-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5350f-112">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="5350f-112">**/h**[**elp**]</span></span>|<span data-ttu-id="5350f-113">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="5350f-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="5350f-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="5350f-114">**/list**</span></span>|<span data-ttu-id="5350f-115">Visualizza tutti gli archivi esistenti dell'utente attualmente connesso,</span><span class="sxs-lookup"><span data-stu-id="5350f-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="5350f-116">inclusi gli archivi di tutte le applicazioni e di tutti gli assembly eseguiti da tale utente.</span><span class="sxs-lookup"><span data-stu-id="5350f-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="5350f-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="5350f-117">**/machine**</span></span>|<span data-ttu-id="5350f-118">Seleziona l'archivio computer.</span><span class="sxs-lookup"><span data-stu-id="5350f-118">Selects the machine store.</span></span> <span data-ttu-id="5350f-119">Usare questa opzione con l'opzione **/list** o **/remove** per specificare che l'operazione deve essere applicata all'archivio computer.</span><span class="sxs-lookup"><span data-stu-id="5350f-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="5350f-120">Questa è una nuova opzione di .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="5350f-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="5350f-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="5350f-121">**/quiet**</span></span>|<span data-ttu-id="5350f-122">Specifica la modalità non interattiva. Evita la visualizzazione dell'output informativo, in modo che vengano visualizzati solo i messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="5350f-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="5350f-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="5350f-123">**/remove**</span></span>|<span data-ttu-id="5350f-124">Rimuove definitivamente tutti gli archivi esistenti dell'utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="5350f-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="5350f-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="5350f-125">**/roaming**</span></span>|<span data-ttu-id="5350f-126">Seleziona l'archivio roaming.</span><span class="sxs-lookup"><span data-stu-id="5350f-126">Selects the roaming store.</span></span> <span data-ttu-id="5350f-127">Usare questa opzione con l'opzione **/list** o **/remove** per specificare che l'operazione deve essere applicata all'archivio roaming.</span><span class="sxs-lookup"><span data-stu-id="5350f-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="5350f-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="5350f-128">**/?**</span></span>|<span data-ttu-id="5350f-129">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="5350f-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5350f-130">Note</span><span class="sxs-lookup"><span data-stu-id="5350f-130">Remarks</span></span>  
 <span data-ttu-id="5350f-131">Se si esegue Storeadm.exe dalla riga di comando senza specificare alcuna opzione, verranno visualizzate la sintassi e le opzioni dello strumento.</span><span class="sxs-lookup"><span data-stu-id="5350f-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="5350f-132">Le opzioni **/list** e **/remove** sono in genere usate singolarmente. Se tuttavia vengono specificate due o più opzioni, queste verranno eseguite nell'ordine in cui sono state immesse sulla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5350f-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="5350f-133">Le applicazioni possono scegliere di salvare i dati in uno di due archivi relativi a un utente o nell'archivio computer:</span><span class="sxs-lookup"><span data-stu-id="5350f-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="5350f-134">L'archivio locale si trova in un percorso per cui è escluso il roaming (in Windows 2000 e versioni successive) anche se per l'utente è abilitato il roaming dei dati.</span><span class="sxs-lookup"><span data-stu-id="5350f-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="5350f-135">L'archivio roaming si trova in un percorso in cui il roaming è consentito, ma solo se è abilitato anche per l'utente attraverso l'amministrazione di Windows NT.</span><span class="sxs-lookup"><span data-stu-id="5350f-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="5350f-136">L'archivio computer è comune a tutti gli utenti di un computer e quindi si trova in una directory comune del computer.</span><span class="sxs-lookup"><span data-stu-id="5350f-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5350f-137">L'archivio computer è stato introdotto con .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="5350f-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="5350f-138">L'eventuale abilitazione del roaming per l'utente non ha alcun effetto sull'amministrazione di Storeadm.exe.</span><span class="sxs-lookup"><span data-stu-id="5350f-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="5350f-139">Se lo strumento viene eseguito senza opzioni, tutte le operazioni verranno applicate all'archivio locale.</span><span class="sxs-lookup"><span data-stu-id="5350f-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="5350f-140">Se lo strumento viene eseguito con l'opzione **/roaming**, tutte le operazioni verranno applicate all'archivio abilitato al roaming.</span><span class="sxs-lookup"><span data-stu-id="5350f-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="5350f-141">Se lo strumento viene eseguito con l'opzione **/machine**, tutte le operazioni verranno applicate all'archivio computer.</span><span class="sxs-lookup"><span data-stu-id="5350f-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5350f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5350f-142">See Also</span></span>  
 [<span data-ttu-id="5350f-143">Strumenti</span><span class="sxs-lookup"><span data-stu-id="5350f-143">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="5350f-144">Spazio di memorizzazione isolato</span><span class="sxs-lookup"><span data-stu-id="5350f-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="5350f-145">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="5350f-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
