---
title: Implementazione del pattern di controllo Window di automazione interfaccia utente
description: Esaminare le linee guida e le convenzioni per implementare il pattern di controllo Window in automazione interfaccia utente. Conosce i membri obbligatori per l'interfaccia IWindowProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: e1d7429f86896947a10b73965caa7d771f54490b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168183"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a>Implementazione del pattern di controllo Window di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IWindowProvider>, incluse le informazioni relative a proprietà, metodi ed eventi di <xref:System.Windows.Automation.WindowPattern> . Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il <xref:System.Windows.Automation.WindowPattern> pattern di controllo viene usato per supportare i controlli che forniscono funzionalità fondamentali basate su finestra all'interno di un'interfaccia utente grafica (GUI) tradizionale. Esempi di controlli che devono implementare questo pattern di controllo sono le finestre dell'applicazione di primo livello, le finestre figlio dell'interfaccia a documenti multipli (MDI), i controlli del riquadro suddiviso ridimensionabili, le finestre di dialogo modali e le finestre della guida del fumetto.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Window, tenere presenti le linee guida e le convenzioni seguenti:  
  
- Per supportare la possibilità di modificare sia le dimensioni della finestra che la posizione sullo schermo con Automazione interfaccia utente, un controllo deve implementare <xref:System.Windows.Automation.Provider.ITransformProvider> oltre a <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- I controlli contenenti barre del titolo ed elementi della barra del titolo che consentono di spostare, ridimensionare, ingrandire, ridurre a icona o chiudere il controllo in genere devono implementare <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- I controlli come i popup di descrizione comando e le caselle combinate o i menu a discesa in genere non implementano <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- Le finestre fumetto della Guida si distinguono dai popup di descrizione comando di base per il provisioning di un pulsante Chiudi simile a quello delle finestre.  
  
- La modalità schermo intero non è supportata da IWindowProvider perché è una funzionalità specifica delle applicazioni e non è un comportamento tipico delle finestre.  
  
<a name="Required_Members_for_IWindowProvider"></a>
## <a name="required-members-for-iwindowprovider"></a>Membri obbligatori per IWindowProvider  
 Le proprietà, i metodi e gli eventi seguenti sono obbligatori per l'implementazione dell'interfaccia IWindowProvider.  
  
|Membro obbligatorio|Tipo di membro|Note|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Event|Nessuno|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Event|Nessuno|  
|<xref:System.Windows.Automation.WindowInteractionState>|Event|Non è garantito che sia <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction>|  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> -Quando un controllo non supporta un comportamento richiesto.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> -Quando il parametro non è un numero valido.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Panoramica dell'albero di automazione dell'interfaccia utente](ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](use-caching-in-ui-automation.md)
