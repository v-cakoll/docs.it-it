---
title: Clrver.exe (Strumento della versione CLR)
description: Esaminare Clrver.exe, lo strumento della versione CLR. Questo strumento segnala tutte le versioni installate del Common Language Runtime (CLR) nel computer.
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: e914034819418df00438c454e209e6c86779ba3c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167273"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="6d3a4-104">Clrver.exe (Strumento della versione CLR)</span><span class="sxs-lookup"><span data-stu-id="6d3a4-104">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="6d3a4-105">Lo strumento della versione CLR (Clrver.exe) segnala tutte le versioni di CRL (Common Language Runtime) installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="6d3a4-106">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="6d3a4-107">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="6d3a4-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="6d3a4-108">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="6d3a4-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="6d3a4-109">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6d3a4-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d3a4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d3a4-110">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="6d3a4-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6d3a4-111">Options</span></span>  
  
|<span data-ttu-id="6d3a4-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="6d3a4-112">Option</span></span>|<span data-ttu-id="6d3a4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d3a4-113">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="6d3a4-114">Visualizza tutti i processi sul computer che utilizzano CLR.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-114">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="6d3a4-115">*PID*</span><span class="sxs-lookup"><span data-stu-id="6d3a4-115">*pid*</span></span>|<span data-ttu-id="6d3a4-116">Visualizza le versioni di CLR utilizzate dal processo con l'ID processo (PID) specificato.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-116">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="6d3a4-117">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-117">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d3a4-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6d3a4-118">Remarks</span></span>  
 <span data-ttu-id="6d3a4-119">Se si chiama Clrver.exe senza opzioni, vengono visualizzate tutte le versioni CLR installate.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-119">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="6d3a4-120">Se si specifica un PID per un altro utente, è necessario disporre di autorizzazioni amministrative per ottenere le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-120">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d3a4-121">In Windows Vista e versioni successive i privilegi di un utente sono determinati dalla funzionalità Controllo dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-121">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="6d3a4-122">Ai membri del gruppo Administrators predefinito vengono assegnati due token di accesso in fase di esecuzione, ovvero un token di accesso utente standard e un token di accesso amministratore.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-122">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="6d3a4-123">Per impostazione predefinita, viene assegnato il ruolo dell'utente standard.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-123">By default, you are in the standard user role.</span></span> <span data-ttu-id="6d3a4-124">Per eseguire il codice che richiede autorizzazioni amministrative, è innanzitutto necessario elevare i propri privilegi da utente standard ad amministratore.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-124">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="6d3a4-125">A tale scopo, all'avvio del prompt dei comandi fare clic con il pulsante destro del mouse sull'icona del prompt dei comandi e indicare che si desidera eseguirlo come amministratore.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-125">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="6d3a4-126">Se si tenta di determinare la versione di CLR per i processi SYSTEM, LOCAL SERVICE e NETWORK SERVICE, viene visualizzato un messaggio che indica che il PID non esiste.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-126">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6d3a4-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="6d3a4-127">Examples</span></span>  
 <span data-ttu-id="6d3a4-128">Il comando che segue visualizza tutte le versioni di CLR installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-128">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="6d3a4-129">Il comando che segue visualizza la versione di CLR utilizzata dal processo 128.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-129">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="6d3a4-130">Il comando che segue visualizza tutti i processi gestiti e la versione di CLR utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6d3a4-130">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="6d3a4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d3a4-131">See also</span></span>

- [<span data-ttu-id="6d3a4-132">Strumenti</span><span class="sxs-lookup"><span data-stu-id="6d3a4-132">Tools</span></span>](index.md)
- [<span data-ttu-id="6d3a4-133">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="6d3a4-133">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
