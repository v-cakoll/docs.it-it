---
title: Cenni preliminari sulla sicurezza di automazione interfaccia utente
description: Leggi una panoramica del modello di sicurezza per l'automazione interfaccia utente Microsoft. Informazioni sul controllo dell'account utente, sulle attività che richiedono privilegi più elevati e sui file manifesto.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
ms.openlocfilehash: d483f282db8ce8e5653d6d83361fa44df05f63f5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163139"
---
# <a name="ui-automation-security-overview"></a>Cenni preliminari sulla sicurezza di automazione interfaccia utente

> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).

In questa panoramica viene descritto il modello di sicurezza per [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] in Windows Vista.

<a name="User_Account_Control"></a>

## <a name="user-account-control"></a>Controllo dell'account utente

La sicurezza è un obiettivo principale di Windows Vista e tra le innovazioni è la possibilità per gli utenti di essere eseguiti come utenti standard (non amministratori) senza necessariamente impedire l'esecuzione di applicazioni e servizi che richiedono privilegi più elevati.

In Windows Vista, la maggior parte delle applicazioni viene fornita con un token standard o amministrativo. Per impostazione predefinita, se un'applicazione non può essere identificata come applicazione amministrativa, viene avviata come applicazione standard. Prima che un'applicazione identificata come amministrativa possa essere avviata, Windows Vista chiede all'utente il consenso per eseguire l'applicazione con privilegi elevati. La richiesta di consenso viene visualizzata per impostazione predefinita, anche se l'utente è membro del gruppo Administrators locale, perché gli amministratori operano come utenti standard finché un'applicazione o un componente di sistema, per cui sono necessarie credenziali amministrative, non richiede l'autorizzazione per l'esecuzione.

<a name="Tasks_Requiring_Higher_Privileges"></a>

## <a name="tasks-requiring-higher-privileges"></a>Attività che richiedono privilegi più elevati

Quando un utente tenta di eseguire un'attività che richiede privilegi amministrativi, Windows Vista Visualizza una finestra di dialogo in cui viene chiesto all'utente il consenso per continuare. Questa finestra di dialogo è protetta dalla comunicazione tra processi, in modo che un software dannoso non possa simulare l'input utente. Analogamente, la schermata di accesso al desktop in genere non è accessibile ad altri processi.

I client di automazione interfaccia utente devono comunicare con altri processi, alcuni dei quali potrebbero essere in esecuzione con un livello di privilegi più elevato. I client potrebbero anche aver bisogno di accedere alle finestre di dialogo di sistema che non sono in genere visibili ad altri processi. Di conseguenza, i client di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono essere considerati attendibili dal sistema e devono essere eseguiti con privilegi speciali.

Per essere considerate attendibili e comunicare con applicazioni in esecuzione con un livello di privilegi più elevato, le applicazioni devono essere firmate.

<a name="Manifest_Files"></a>

## <a name="manifest-files"></a>File manifesto

Per ottenere l'accesso all'interfaccia utente del sistema protetto, le applicazioni devono essere compilate con un file manifesto che include l' `uiAccess` attributo nel `requestedExecutionLevel` tag, come indicato di seguito:

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

`uiAccess`è "false" per impostazione predefinita. ovvero, se l'attributo viene omesso o se non è presente alcun manifesto per l'assembly, l'applicazione non sarà in grado di ottenere l'accesso all'interfaccia utente protetta.
