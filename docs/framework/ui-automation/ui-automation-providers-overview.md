---
title: Cenni preliminari sui provider di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, providers
- providers, UI Automation
ms.assetid: 859557b8-51e1-4d15-92e8-318d2dcdb2f7
ms.openlocfilehash: 1f780ffc37b0aff93a3358c1980d271fe10c1321
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179881"
---
# <a name="ui-automation-providers-overview"></a>Cenni preliminari sui provider di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 I provider di automazione interfaccia utente abilitano la comunicazione dei controlli con le applicazioni client di automazione interfaccia utente. In generale, ogni controllo o un altro elemento distinto in una [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] è rappresentato da un provider. Il provider espone informazioni sull'elemento e facoltativamente implementa i pattern di controllo che consentono all'applicazione client di interagire con il controllo.  
  
 Le applicazioni client in genere non devono interagire direttamente con i provider. La maggior parte dei controlli standard nelle applicazioni che [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] utilizzano Win32, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Windows Form o framework vengono esposti automaticamente al sistema. Le applicazioni che implementano controlli personalizzati possono anche implementare i provider di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per tali controlli. Le applicazioni client non devono eseguire passaggi speciali aggiuntivi per avervi accesso.  
  
 In questo argomento viene fornita [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] una panoramica di come gli sviluppatori di controlli implementano i provider, in particolare per i controlli nelle finestre Windows Form e Win32.This topic provides an overview of how control developers implement providers, particularly for controls in Windows Forms and Win32 windows.  
  
<a name="Types_of_Providers"></a>
## <a name="types-of-providers"></a>Tipi di provider  
 I provider di automazione interfaccia utente rientrano in due categorie, ovvero provider lato client e provider lato server.  
  
### <a name="client-side-providers"></a>Provider lato client  
 I provider lato client vengono implementati dai client di automazione interfaccia utente per comunicare con un'applicazione che non supporta parzialmente o completamente [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. I provider lato client in genere comunicano con il server attraverso i limiti del processo inviando e ricevendo messaggi di Windows.  
  
 Poiché i provider di automazione interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] per i controlli in Win32, Windows Form o applicazioni vengono forniti come parte del sistema operativo, le applicazioni client raramente devono implementare i propri provider e questa panoramica non li copre ulteriormente.  
  
### <a name="server-side-providers"></a>Provider lato server  
 I provider sul lato server vengono implementati da controlli personalizzati o da applicazioni basate [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]su un framework dell'interfaccia utente diverso da Win32, Windows Form o .  
  
 I provider lato server comunicano con le applicazioni client attraverso il limite di processo esponendo le interfacce al sistema principale di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , che a sua volta gestisce le richieste dai client.  
  
<a name="AutomationProviderConcepts"></a>
## <a name="ui-automation-provider-concepts"></a>Concetti relativi al provider di automazione interfaccia utente  
 In questa sezione viene presentata una breve spiegazione di alcuni concetti chiave fondamentali per l'implementazione di provider di automazione interfaccia utente.  
  
### <a name="elements"></a>Elementi  
 Gli elementi di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sono parti dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] visibili ai client di automazione interfaccia utente, ad esempio finestre delle applicazioni, riquadri, pulsanti, descrizioni comandi, caselle di riepilogo e voci di elenco.  
  
### <a name="navigation"></a>Navigazione  
 Gli elementi di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vengono esposti ai client sotto forma di albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] genera l'albero passando da un elemento a un altro. Lo spostamento è abilitato per i provider per ogni elemento, ciascuno dei quali può puntare a un elemento padre, di pari livello e figlio.  
  
 Per altre informazioni sulla visualizzazione client dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
### <a name="views"></a>Viste  
 Un client può vedere l'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] nelle tre visualizzazioni principali, come illustrato nella tabella seguente.  
  
|||  
|-|-|  
|Visualizzazione non elaborata|Contiene tutti gli elementi.|  
|Visualizzazione controlli|Contiene elementi che sono controlli.|  
|Visualizzazione contenuto|Contiene elementi che includono contenuti.|  
  
 Per altre informazioni sulle visualizzazioni client dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 È responsabilità dell'implementazione del provider definire un elemento come elemento contenuto o elemento controllo. Gli elementi controllo possono essere anche elementi contenuto, mentre tutti gli elementi contenuto sono elementi controllo.  
  
### <a name="frameworks"></a>Framework  
 Un framework è un componente che gestisce controlli figlio, hit testing e rendering in un'area dello schermo. Ad esempio, una finestra Win32, spesso definita HWND, può fungere da framework che contiene più [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementi, ad esempio una barra dei menu, una barra di stato e pulsanti.  
  
 I controlli contenitore Win32, ad esempio caselle di riepilogo e visualizzazioni struttura ad albero, sono considerati framework, perché contengono il proprio codice per il rendering di elementi figlio e l'esecuzione di hit testing su di essi. Per contro, una casella di testo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] non è un framework perché i processi di rendering  e hit testing sono gestiti dalla finestra [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che la contiene.  
  
 L' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in un'applicazione può essere costituita da diversi framework. Ad esempio, una finestra dell'applicazione HWND potrebbe contenere HTML dinamico (DHTML) che a sua volta contiene un componente, ad esempio una casella combinata in un HWND.  
  
### <a name="fragments"></a>Frammenti  
 Un frammento è un sottoalbero completo di elementi di un determinato framework. L'elemento in corrispondenza del nodo radice del sottoalbero è definito radice del frammento. Una radice del frammento non ha un elemento padre, ma è ospitata all'interno di un altro framework, in genere una finestra Win32 (HWND).  
  
### <a name="hosts"></a>Hosts  
 Il nodo radice di ogni frammento deve essere ospitato in un elemento, in genere una finestra Win32 (HWND). L'eccezione è rappresentata dal desktop, che non è ospitato in nessun altro elemento. L'host di un controllo personalizzato è HWND del controllo stesso e non la finestra dell'applicazione o qualsiasi altra finestra che potrebbe contenere gruppi di controlli di primo livello.  
  
 L'host di un frammento ha un ruolo importante nell'implementazione dei servizi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Consente lo spostamento alla radice del frammento e rende disponibili alcune proprietà predefinite in modo che il provider personalizzato debba implementarle.  
  
## <a name="see-also"></a>Vedere anche

- [Implementazione del provider di automazione interfaccia utente lato server](server-side-ui-automation-provider-implementation.md)
