---
title: Cenni preliminari sulla sicurezza di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b35014993f10c3a60c16f784e7dd11b9a20f4f4c
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032543"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="dc0a9-102">Cenni preliminari sulla sicurezza di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dc0a9-102">UI Automation Security Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="dc0a9-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dc0a9-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dc0a9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dc0a9-105">Questa panoramica descrive il modello di sicurezza per [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc0a9-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].</span></span>  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a><span data-ttu-id="dc0a9-106">Controllo dell'account utente</span><span class="sxs-lookup"><span data-stu-id="dc0a9-106">User Account Control</span></span>  
 <span data-ttu-id="dc0a9-107">La sicurezza è un obiettivo fondamentale di [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] e una delle novità è la possibilità per gli utenti di operare come utenti standard (non amministratori) senza che venga bloccata l'esecuzione di applicazioni e servizi che richiedono privilegi più elevati.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-107">Security is a major focus of [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>  
  
 <span data-ttu-id="dc0a9-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], la maggior parte delle applicazioni viene fornita con un token standard o amministrativo.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-108">In [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)], most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="dc0a9-109">Per impostazione predefinita, se un'applicazione non può essere identificata come applicazione amministrativa, viene avviata come applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="dc0a9-110">Prima che un'applicazione identificata come amministrativa possa essere avviata, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] chiede all'utente il consenso per eseguire l'applicazione come utente con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-110">Before an application identified as administrative can be launched, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="dc0a9-111">La richiesta di consenso viene visualizzata per impostazione predefinita, anche se l'utente è membro del gruppo Administrators locale, perché gli amministratori operano come utenti standard finché un'applicazione o un componente di sistema, per cui sono necessarie credenziali amministrative, non richiede l'autorizzazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="dc0a9-112">Attività che richiedono privilegi più elevati</span><span class="sxs-lookup"><span data-stu-id="dc0a9-112">Tasks Requiring Higher Privileges</span></span>  
 <span data-ttu-id="dc0a9-113">Quando un utente tenta di eseguire un'attività che richiede privilegi amministrativi, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] visualizza una finestra di dialogo che chiede all'utente il consenso per continuare.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-113">When a user attempts to perform a task that requires administrative privileges, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="dc0a9-114">Questa finestra di dialogo è protetta dalla comunicazione tra processi, in modo che un software dannoso non possa simulare l'input utente.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="dc0a9-115">Analogamente, la schermata di accesso al desktop in genere non è accessibile ad altri processi.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>  
  
 <span data-ttu-id="dc0a9-116">I client di automazione interfaccia utente devono comunicare con altri processi, alcuni dei quali potrebbero essere in esecuzione con un livello di privilegi più elevato.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="dc0a9-117">I client potrebbero anche aver bisogno di accedere alle finestre di dialogo di sistema che non sono in genere visibili ad altri processi.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="dc0a9-118">Di conseguenza, i client di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono essere considerati attendibili dal sistema e devono essere eseguiti con privilegi speciali.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>  
  
 <span data-ttu-id="dc0a9-119">Per essere considerate attendibili e comunicare con applicazioni in esecuzione con un livello di privilegi più elevato, le applicazioni devono essere firmate.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a><span data-ttu-id="dc0a9-120">File manifesto</span><span class="sxs-lookup"><span data-stu-id="dc0a9-120">Manifest Files</span></span>  
 <span data-ttu-id="dc0a9-121">Per accedere all' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]di  sistema protetta, le applicazioni devono essere compilate con un file manifesto che include un attributo speciale.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-121">To gain access to the protected system [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], applications must be built with a manifest file that includes a special attribute in the manifest file.</span></span> <span data-ttu-id="dc0a9-122">Questo attributo `uiAccess` è incluso nel tag `requestedExecutionLevel` , come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc0a9-122">This `uiAccess` attribute is included in the `requestedExecutionLevel` tag, as follows:</span></span>  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 <span data-ttu-id="dc0a9-123">Il valore dell'attributo `level` in questo codice è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-123">The value of the `level` attribute in this code is an example only.</span></span>  
  
 <span data-ttu-id="dc0a9-124">`UIAccess` è "false" per impostazione predefinita, ovvero, se l'attributo viene omesso o se non esiste alcun manifesto per l'assembly, l'applicazione non sarà in grado di accedere all' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]protetta.</span><span class="sxs-lookup"><span data-stu-id="dc0a9-124">`UIAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="dc0a9-125">Per ulteriori informazioni sul [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] sicurezza, sulla firma delle applicazioni e sulla creazione di manifesti dell'assembly, vedere "Per gli sviluppatori migliori procedure consigliate e linee guida per le applicazioni in un con privilegi ambiente minimi" su [MSDN](https://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span><span class="sxs-lookup"><span data-stu-id="dc0a9-125">For more information on [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] security, on signing applications, and on creating assembly manifests, see "Developer Best Practices and Guidelines for Applications in a Least Privileged Environment" on  [MSDN](https://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).</span></span>
