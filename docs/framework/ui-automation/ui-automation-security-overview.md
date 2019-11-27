---
title: Cenni preliminari sulla sicurezza di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: 70d24c3dcc531abcec6d4dce75b5f0b31757e0c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448778"
---
# <a name="ui-automation-security-overview"></a><span data-ttu-id="e13fb-102">Cenni preliminari sulla sicurezza di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e13fb-102">UI Automation Security Overview</span></span>

> [!NOTE]
> <span data-ttu-id="e13fb-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="e13fb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e13fb-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e13fb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="e13fb-105">In questa panoramica viene descritto il modello di sicurezza per [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e13fb-105">This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.</span></span>

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a><span data-ttu-id="e13fb-106">Controllo account utente</span><span class="sxs-lookup"><span data-stu-id="e13fb-106">User Account Control</span></span>

<span data-ttu-id="e13fb-107">La sicurezza è un obiettivo principale di Windows Vista e tra le innovazioni è la possibilità per gli utenti di essere eseguiti come utenti standard (non amministratori) senza necessariamente impedire l'esecuzione di applicazioni e servizi che richiedono privilegi più elevati.</span><span class="sxs-lookup"><span data-stu-id="e13fb-107">Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.</span></span>

<span data-ttu-id="e13fb-108">In Windows Vista, la maggior parte delle applicazioni viene fornita con un token standard o amministrativo.</span><span class="sxs-lookup"><span data-stu-id="e13fb-108">In Windows Vista, most applications are supplied with either a standard or an administrative token.</span></span> <span data-ttu-id="e13fb-109">Per impostazione predefinita, se un'applicazione non può essere identificata come applicazione amministrativa, viene avviata come applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="e13fb-109">If an application cannot be identified as an administrative application, it is launched as a standard application by default.</span></span> <span data-ttu-id="e13fb-110">Prima che un'applicazione identificata come amministrativa possa essere avviata, Windows Vista chiede all'utente il consenso per eseguire l'applicazione con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="e13fb-110">Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated.</span></span> <span data-ttu-id="e13fb-111">La richiesta di consenso viene visualizzata per impostazione predefinita, anche se l'utente è membro del gruppo Administrators locale, perché gli amministratori operano come utenti standard finché un'applicazione o un componente di sistema, per cui sono necessarie credenziali amministrative, non richiede l'autorizzazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e13fb-111">The consent prompt is displayed by default, even if the user is a member of the local Administrators group, because administrators run as standard users until an application or system component that requires administrative credentials requests permission to run.</span></span>

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a><span data-ttu-id="e13fb-112">Attività che richiedono privilegi più elevati</span><span class="sxs-lookup"><span data-stu-id="e13fb-112">Tasks Requiring Higher Privileges</span></span>

<span data-ttu-id="e13fb-113">Quando un utente tenta di eseguire un'attività che richiede privilegi amministrativi, Windows Vista Visualizza una finestra di dialogo in cui viene chiesto all'utente il consenso per continuare.</span><span class="sxs-lookup"><span data-stu-id="e13fb-113">When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue.</span></span> <span data-ttu-id="e13fb-114">Questa finestra di dialogo è protetta dalla comunicazione tra processi, in modo che un software dannoso non possa simulare l'input utente.</span><span class="sxs-lookup"><span data-stu-id="e13fb-114">This dialog box is protected from cross-process communication, so that malicious software cannot simulate user input.</span></span> <span data-ttu-id="e13fb-115">Analogamente, la schermata di accesso al desktop in genere non è accessibile ad altri processi.</span><span class="sxs-lookup"><span data-stu-id="e13fb-115">Similarly, the desktop logon screen cannot normally be accessed by other processes.</span></span>

<span data-ttu-id="e13fb-116">I client di automazione interfaccia utente devono comunicare con altri processi, alcuni dei quali potrebbero essere in esecuzione con un livello di privilegi più elevato.</span><span class="sxs-lookup"><span data-stu-id="e13fb-116">UI Automation clients must communicate with other processes, some of them perhaps running at a higher privilege level.</span></span> <span data-ttu-id="e13fb-117">I client potrebbero anche aver bisogno di accedere alle finestre di dialogo di sistema che non sono in genere visibili ad altri processi.</span><span class="sxs-lookup"><span data-stu-id="e13fb-117">Clients also might need access to the system dialog boxes that are not normally visible to other processes.</span></span> <span data-ttu-id="e13fb-118">Di conseguenza, i client di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono essere considerati attendibili dal sistema e devono essere eseguiti con privilegi speciali.</span><span class="sxs-lookup"><span data-stu-id="e13fb-118">Therefore, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clients must be trusted by the system, and must run with special privileges.</span></span>

<span data-ttu-id="e13fb-119">Per essere considerate attendibili e comunicare con applicazioni in esecuzione con un livello di privilegi più elevato, le applicazioni devono essere firmate.</span><span class="sxs-lookup"><span data-stu-id="e13fb-119">To be trusted to communicate with applications running at a higher privilege level, applications must be signed.</span></span>

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a><span data-ttu-id="e13fb-120">File manifesto</span><span class="sxs-lookup"><span data-stu-id="e13fb-120">Manifest Files</span></span>

<span data-ttu-id="e13fb-121">Per ottenere l'accesso all'interfaccia utente del sistema protetto, le applicazioni devono essere compilate con un file manifesto che includa l'attributo `uiAccess` nel tag `requestedExecutionLevel`, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e13fb-121">To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:</span></span>

```xml
<trustInfo xmlns="urn:schemas-microsoft-com:asm.v3">
  <security>
    <requestedPrivileges>
      <requestedExecutionLevel
        level="highestAvailable"
        uiAccess="true" />
    </requestedPrivileges>
  </security>
</trustInfo>
```

<span data-ttu-id="e13fb-122">Il valore dell'attributo `level` in questo codice è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="e13fb-122">The value of the `level` attribute in this code is an example only.</span></span>

<span data-ttu-id="e13fb-123">per impostazione predefinita, `uiAccess` è "false"; ovvero, se l'attributo viene omesso o se non è presente alcun manifesto per l'assembly, l'applicazione non sarà in grado di ottenere l'accesso all'interfaccia utente protetta.</span><span class="sxs-lookup"><span data-stu-id="e13fb-123">`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.</span></span>
