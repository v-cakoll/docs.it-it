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
# <a name="ui-automation-security-overview"></a>Cenni preliminari sulla sicurezza di automazione interfaccia utente

> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).

This overview describes the security model for [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Controllo dell'account utente

Security is a major focus of Windows Vista and among the innovations is the ability for users to run as standard (non-administrator) users without necessarily being blocked from running applications and services that require higher privileges.

In Windows Vista, most applications are supplied with either a standard or an administrative token. Per impostazione predefinita, se un'applicazione non può essere identificata come applicazione amministrativa, viene avviata come applicazione standard. Before an application identified as administrative can be launched, Windows Vista prompts the user for consent to run the application as elevated. La richiesta di consenso viene visualizzata per impostazione predefinita, anche se l'utente è membro del gruppo Administrators locale, perché gli amministratori operano come utenti standard finché un'applicazione o un componente di sistema, per cui sono necessarie credenziali amministrative, non richiede l'autorizzazione per l'esecuzione.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Attività che richiedono privilegi più elevati

When a user attempts to perform a task that requires administrative privileges, Windows Vista presents a dialog box asking the user for consent to continue. Questa finestra di dialogo è protetta dalla comunicazione tra processi, in modo che un software dannoso non possa simulare l'input utente. Analogamente, la schermata di accesso al desktop in genere non è accessibile ad altri processi.

I client di automazione interfaccia utente devono comunicare con altri processi, alcuni dei quali potrebbero essere in esecuzione con un livello di privilegi più elevato. I client potrebbero anche aver bisogno di accedere alle finestre di dialogo di sistema che non sono in genere visibili ad altri processi. Di conseguenza, i client di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono essere considerati attendibili dal sistema e devono essere eseguiti con privilegi speciali.

Per essere considerate attendibili e comunicare con applicazioni in esecuzione con un livello di privilegi più elevato, le applicazioni devono essere firmate.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>File manifesto

To gain access to the protected system UI, applications must be built with a manifest file that includes the `uiAccess` attribute in the `requestedExecutionLevel` tag, as follows:

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

Il valore dell'attributo `level` in questo codice è solo un esempio.

`uiAccess` is "false" by default; that is, if the attribute is omitted, or if there is no manifest for the assembly, the application will not be able to gain access to protected UI.
