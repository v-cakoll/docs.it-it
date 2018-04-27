---
title: Implementazione dei provider di automazione interfaccia utente sul lato client
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
caps.latest.revision: 14
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 09f54098c34d835c04a18b16dc5e33c7ebed5edb
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="client-side-ui-automation-provider-implementation"></a>Implementazione dei provider di automazione interfaccia utente sul lato client
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Vengono usati più framework [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] diversi nei sistemi operativi [!INCLUDE[TLA#tla_ms](../../../includes/tlasharptla-ms-md.md)] , tra cui [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]e [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] espone informazioni sugli elementi dell'interfaccia utente ai client. Tuttavia, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] è in grado di differenziare i vari tipi di controlli esistenti in tali framework e le tecniche necessarie per estrarre informazioni da essi. Queste attività vengono invece demandate a oggetti denominati provider. Un provider estrae le informazioni da un controllo specifico e inoltra tali informazioni a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], che quindi le visualizza al client in modo coerente.  
  
 I provider possono esistere sul lato server o sul lato client. Un provider lato server è implementato dal controllo stesso. Gli elementi[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] implementano provider, così come qualsiasi controllo di terze parti scritto in base a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Tuttavia, i controlli di versioni precedenti, ad esempio quelli in [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] , non supportano direttamente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Questi controlli vengono invece gestiti da provider presenti nel processo client e ottengono informazioni sui controlli mediante la comunicazione tra processi, ad esempio monitorando i messaggi delle finestre da e verso i controlli. Questi provider lato client vengono talvolta definiti proxy.  
  
 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] implementa provider per standard [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] e controlli Windows Form. Inoltre, un provider di fallback offre supporto [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] parziale a qualsiasi controllo che non è servito da un altro provider lato server o un proxy ma che ha un'implementazione [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] . Tutti questi provider vengono caricati automaticamente e sono disponibili per le applicazioni client.  
  
 Per ulteriori informazioni sul supporto per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] e controlli Windows Form, vedere [il supporto di automazione interfaccia utente per i controlli Standard](../../../docs/framework/ui-automation/ui-automation-support-for-standard-controls.md).  
  
 Le applicazioni possono inoltre registrare altri provider lato client.  
  
<a name="Distributing_Client-Side_Providers"></a>   
## <a name="distributing-client-side-providers"></a>Distribuzione di provider lato client  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] prevede di trovare un provider lato client in un assembly gestito a livello di codice. Lo spazio dei nomi in questo assembly deve avere lo stesso nome dell'assembly. Ad esempio, un assembly denominato ContosoProxies.dll conterrà lo spazio dei nomi ContosoProxies. Nello spazio dei nomi creare una classe <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> . Nell'implementazione del campo statico <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> creare una matrice di strutture <xref:System.Windows.Automation.ClientSideProviderDescription> che descrivono i provider.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>   
## <a name="registering-and-configuring-client-side-providers"></a>Registrazione e configurazione dei provider lato client  
 I provider lato client in una [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] vengono caricati chiamando <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>. Non sono richieste altre azioni da parte di un'applicazione client per usare i provider.  
  
 I provider implementati nel codice del client vengono registrati tramite <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>. Questo metodo accetta come argomento una matrice di strutture <xref:System.Windows.Automation.ClientSideProviderDescription> , ognuna delle quali specifica le proprietà seguenti:  
  
-   Una funzione di callback che crea l'oggetto provider.  
  
-   Il nome della classe dei controlli che il provider gestirà.  
  
-   Il nome dell'immagine dell'applicazione (in genere il nome completo del file eseguibile) che il provider gestirà.  
  
-   I flag che controllano il modo in cui il nome della classe è associato alle classi di finestra disponibili nell'applicazione di destinazione.  
  
 Gli ultimi due parametri sono facoltativi. Il client può specificare il nome dell'immagine dell'applicazione di destinazione quando desidera usare provider diversi per applicazioni diverse. Ad esempio, il client potrebbe usare un provider per un controllo visualizzazione elenco [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] in un'applicazione nota che supporta il pattern MultipleView e un altro per un controllo simile in un'altra applicazione nota che non lo supporta.  
  
## <a name="see-also"></a>Vedere anche  
 [Creare un provider di automazione interfaccia utente lato client](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)  
 [Implementare provider di automazione interfaccia utente in un'applicazione client](../../../docs/framework/ui-automation/implement-ui-automation-providers-in-a-client-application.md)
