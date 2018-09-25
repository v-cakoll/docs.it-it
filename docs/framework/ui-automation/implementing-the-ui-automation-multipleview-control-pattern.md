---
title: Implementazione del pattern di controllo MultipleView di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 4fe991aa0a558851ac6b69640e7eac6875df8d4f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47090461"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a>Implementazione del pattern di controllo MultipleView di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, incluse le informazioni relative a eventi e proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.MultipleViewPattern> viene usato per supportare i controlli che implementano più rappresentazioni dello stesso set di informazioni o controlli figlio e che sono in grado di scorrere tali rappresentazioni.  
  
 Esempi di controlli che possono presentare più visualizzazioni includono la visualizzazione elenco (che può visualizzare il proprio contenuto sotto forma di anteprime, riquadri, icone o dettagli), grafici di [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] (a torta, a linee, a barre, valore di cella con una formula), documenti di [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (normale, layout Web, layout di stampa, layout lettura, struttura), calendario di [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] (anno, mese, settimana, giorno) e interfacce [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] . Le visualizzazioni supportate sono determinate dallo sviluppatore del controllo e sono specifiche di ogni controllo.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo MultipleView, tenere presenti le linee guida e le convenzioni seguenti:  
  
-   Anche l'interfaccia<xref:System.Windows.Automation.Provider.IMultipleViewProvider> deve essere implementata in un contenitore che gestisce la visualizzazione corrente se è diversa da un controllo che fornisce la visualizzazione corrente. Ad esempio, Esplora risorse contiene un controllo elenco per il contenuto della cartella corrente, mentre la visualizzazione per il controllo viene gestita dall'applicazione Esplora risorse.  
  
-   Un controllo in grado di ordinare il relativo contenuto non supporta più visualizzazioni.  
  
-   La raccolta di visualizzazioni deve essere identica tra istanze.  
  
-   I nomi delle visualizzazioni devono essere adatti all'uso nelle applicazioni di sintesi vocale o nelle altre applicazioni per la lettura in Braille e altri metodi di lettura.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a>Membri obbligatori per IMultipleViewProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di IMultipleViewProvider.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Metodo|Nessuna|  
  
 Non sono presenti eventi associati a questo pattern di controllo.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Viene eseguita una chiamata a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parametro che non è un membro della raccolta delle visualizzazioni supportate.|  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei pattern di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Supportare pattern di controllo in un provider di automazione interfaccia utente](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Panoramica dell'albero di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Usare la memorizzazione nella cache in automazione interfaccia utente](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
