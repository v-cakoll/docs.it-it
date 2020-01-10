---
title: Clrver.exe (strumento della versione CLR)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: bfc612ef5455e1b4a03d15fd99a8a1873d2c7c08
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715791"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="07ff0-102">Clrver.exe (strumento della versione CLR)</span><span class="sxs-lookup"><span data-stu-id="07ff0-102">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="07ff0-103">Lo strumento della versione CLR (Clrver.exe) segnala tutte le versioni di CRL (Common Language Runtime) installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="07ff0-103">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="07ff0-104">Viene installato automaticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="07ff0-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="07ff0-105">Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="07ff0-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="07ff0-106">Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="07ff0-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="07ff0-107">Al prompt dei comandi digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="07ff0-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ff0-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07ff0-108">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="07ff0-109">Options</span><span class="sxs-lookup"><span data-stu-id="07ff0-109">Options</span></span>  
  
|<span data-ttu-id="07ff0-110">Opzione</span><span class="sxs-lookup"><span data-stu-id="07ff0-110">Option</span></span>|<span data-ttu-id="07ff0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07ff0-111">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="07ff0-112">Visualizza tutti i processi sul computer che utilizzano CLR.</span><span class="sxs-lookup"><span data-stu-id="07ff0-112">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="07ff0-113">*pid*</span><span class="sxs-lookup"><span data-stu-id="07ff0-113">*pid*</span></span>|<span data-ttu-id="07ff0-114">Visualizza le versioni di CLR utilizzate dal processo con l'ID processo (PID) specificato.</span><span class="sxs-lookup"><span data-stu-id="07ff0-114">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="07ff0-115">Visualizza la sintassi e le opzioni di comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="07ff0-115">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07ff0-116">Note</span><span class="sxs-lookup"><span data-stu-id="07ff0-116">Remarks</span></span>  
 <span data-ttu-id="07ff0-117">Se si chiama Clrver.exe senza opzioni, vengono visualizzate tutte le versioni CLR installate.</span><span class="sxs-lookup"><span data-stu-id="07ff0-117">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="07ff0-118">Se si specifica un PID per un altro utente, è necessario disporre di autorizzazioni amministrative per ottenere le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="07ff0-118">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07ff0-119">In Windows Vista e versioni successive i privilegi di un utente sono determinati dalla funzionalità Controllo dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="07ff0-119">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="07ff0-120">Ai membri del gruppo Administrators predefinito vengono assegnati due token di accesso in fase di esecuzione, ovvero un token di accesso utente standard e un token di accesso amministratore.</span><span class="sxs-lookup"><span data-stu-id="07ff0-120">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="07ff0-121">Per impostazione predefinita, viene assegnato il ruolo dell'utente standard.</span><span class="sxs-lookup"><span data-stu-id="07ff0-121">By default, you are in the standard user role.</span></span> <span data-ttu-id="07ff0-122">Per eseguire il codice che richiede autorizzazioni amministrative, è innanzitutto necessario elevare i propri privilegi da utente standard ad amministratore.</span><span class="sxs-lookup"><span data-stu-id="07ff0-122">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="07ff0-123">A tale scopo, all'avvio del prompt dei comandi fare clic con il pulsante destro del mouse sull'icona del prompt dei comandi e indicare che si desidera eseguirlo come amministratore.</span><span class="sxs-lookup"><span data-stu-id="07ff0-123">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="07ff0-124">Se si tenta di determinare la versione di CLR per i processi SYSTEM, LOCAL SERVICE e NETWORK SERVICE, viene visualizzato un messaggio che indica che il PID non esiste.</span><span class="sxs-lookup"><span data-stu-id="07ff0-124">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="07ff0-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="07ff0-125">Examples</span></span>  
 <span data-ttu-id="07ff0-126">Il comando che segue visualizza tutte le versioni di CLR installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="07ff0-126">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="07ff0-127">Il comando che segue visualizza la versione di CLR utilizzata dal processo 128.</span><span class="sxs-lookup"><span data-stu-id="07ff0-127">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="07ff0-128">Il comando che segue visualizza tutti i processi gestiti e la versione di CLR utilizzata.</span><span class="sxs-lookup"><span data-stu-id="07ff0-128">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="07ff0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07ff0-129">See also</span></span>

- [<span data-ttu-id="07ff0-130">Strumenti</span><span class="sxs-lookup"><span data-stu-id="07ff0-130">Tools</span></span>](index.md)
- [<span data-ttu-id="07ff0-131">Prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="07ff0-131">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
