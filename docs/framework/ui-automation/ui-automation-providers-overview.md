---
title: Cenni preliminari sui provider di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 98208f1e1fa1b540bf3880e33478854128505233
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778779"
---
# <a name="ui-automation-providers-overview"></a>Cenni preliminari sui provider di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 I provider di automazione interfaccia utente abilitano la comunicazione dei controlli con le applicazioni client di automazione interfaccia utente. In generale, ogni controllo o un altro elemento distinto in una [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] è rappresentato da un provider. Il provider espone informazioni sull'elemento e facoltativamente implementa i pattern di controllo che consentono all'applicazione client di interagire con il controllo.  
  
 Le applicazioni client in genere non devono interagire direttamente con i provider. La maggior parte dei controlli standard nelle applicazioni che usano i framework Win32, Windows Forms o [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] vengono automaticamente esposti al sistema [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Le applicazioni che implementano controlli personalizzati possono anche implementare i provider di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per tali controlli. Le applicazioni client non devono eseguire passaggi speciali aggiuntivi per avervi accesso.  
  
 Questo argomento fornisce una panoramica del modo in cui gli sviluppatori di controlli implementano i provider di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], in particolare per i controlli nelle finestre Windows Forms e Win32.  
  
<a name="Types_of_Providers"></a>   
## <a name="types-of-providers"></a>Tipi di provider  
 I provider di automazione interfaccia utente rientrano in due categorie, ovvero provider lato client e provider lato server.  
  
### <a name="client-side-providers"></a>Provider lato client  
 I provider lato client vengono implementati dai client di automazione interfaccia utente per comunicare con un'applicazione che non supporta parzialmente o completamente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. I provider lato client in genere comunicano con il server attraverso il limite di processo inviando e ricevendo messaggi di Windows.  
  
 Poiché i provider di automazione interfaccia utente per i controlli nelle applicazioni Win32, Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] sono forniti come parte del sistema operativo, le applicazioni client raramente devono implementare i propri provider e questa panoramica non le copre ulteriormente.  
  
### <a name="server-side-providers"></a>Provider lato server  
 I provider lato server vengono implementati da controlli personalizzati o da applicazioni basate su un Framework dell'interfaccia utente diverso da Win32, Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].  
  
 I provider lato server comunicano con le applicazioni client attraverso il limite di processo esponendo le interfacce al sistema principale di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , che a sua volta gestisce le richieste dai client.  
  
<a name="AutomationProviderConcepts"></a>   
## <a name="ui-automation-provider-concepts"></a>Concetti relativi al provider di automazione interfaccia utente  
 In questa sezione viene presentata una breve spiegazione di alcuni concetti chiave fondamentali per l'implementazione di provider di automazione interfaccia utente.  
  
### <a name="elements"></a>Elementi  
 Gli elementi di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sono parti dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] visibili ai client di automazione interfaccia utente, ad esempio finestre delle applicazioni, riquadri, pulsanti, descrizioni comandi, caselle di riepilogo e voci di elenco.  
  
### <a name="navigation"></a>Navigazione  
 Gli elementi di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vengono esposti ai client sotto forma di albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] genera l'albero passando da un elemento a un altro. Lo spostamento è abilitato per i provider per ogni elemento, ciascuno dei quali può puntare a un elemento padre, di pari livello e figlio.  
  
 Per altre informazioni sulla visualizzazione client dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Visualizzazioni  
 Un client può vedere l'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] nelle tre visualizzazioni principali, come illustrato nella tabella seguente.  
  
|||  
|-|-|  
|Visualizzazione non elaborata|Contiene tutti gli elementi.|  
|Visualizzazione controlli|Contiene elementi che sono controlli.|  
|Visualizzazione Content|Contiene elementi che includono contenuti.|  
  
 Per altre informazioni sulle visualizzazioni client dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 È responsabilità dell'implementazione del provider definire un elemento come elemento contenuto o elemento controllo. Gli elementi controllo possono essere anche elementi contenuto, mentre tutti gli elementi contenuto sono elementi controllo.  
  
### <a name="frameworks"></a>Framework  
 Un framework è un componente che gestisce controlli figlio, hit testing e rendering in un'area dello schermo. Ad esempio, una finestra Win32, spesso denominata HWND, può fungere da Framework che contiene più elementi [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] come una barra dei menu, una barra di stato e pulsanti.  
  
 I controlli contenitore Win32, ad esempio caselle di riepilogo e visualizzazioni albero, sono considerati Framework, perché contengono il proprio codice per il rendering degli elementi figlio e l'esecuzione di hit testing su di essi. Per contro, una casella di testo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] non è un framework perché i processi di rendering  e hit testing sono gestiti dalla finestra [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che la contiene.  
  
 L' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in un'applicazione può essere costituita da diversi framework. Ad esempio, una finestra dell'applicazione HWND potrebbe contenere codice HTML dinamico (DHTML) che a sua volta contiene un componente, ad esempio una casella combinata in un HWND.  
  
### <a name="fragments"></a>Frammenti  
 Un frammento è un sottoalbero completo di elementi di un determinato framework. L'elemento in corrispondenza del nodo radice del sottoalbero è definito radice del frammento. Una radice del frammento non ha un elemento padre, ma è ospitata in un altro Framework, in genere una finestra Win32 (HWND).  
  
### <a name="hosts"></a>Host  
 Il nodo radice di ogni frammento deve essere ospitato in un elemento, in genere una finestra Win32 (HWND). L'eccezione è rappresentata dal desktop, che non è ospitato in nessun altro elemento. L'host di un controllo personalizzato è HWND del controllo stesso e non la finestra dell'applicazione o qualsiasi altra finestra che potrebbe contenere gruppi di controlli di primo livello.  
  
 L'host di un frammento ha un ruolo importante nell'implementazione dei servizi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Consente lo spostamento alla radice del frammento e rende disponibili alcune proprietà predefinite in modo che il provider personalizzato debba implementarle.  
  
## <a name="see-also"></a>Vedere anche

- [Implementazione del provider di automazione interfaccia utente lato server](server-side-ui-automation-provider-implementation.md)
