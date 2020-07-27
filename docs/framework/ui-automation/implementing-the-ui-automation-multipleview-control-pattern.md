---
title: Implementazione del pattern di controllo MultipleView di automazione interfaccia utente
description: Esaminare le linee guida e le convenzioni per implementare il pattern di controllo MultipleView in automazione interfaccia utente. Vedere Membri obbligatori per l'interfaccia IMultipleViewProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 0d65d57637891fcb1307f5ee83a417941ff323fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168223"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a>Implementazione del pattern di controllo MultipleView di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, incluse le informazioni relative a eventi e proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.MultipleViewPattern> viene usato per supportare i controlli che implementano più rappresentazioni dello stesso set di informazioni o controlli figlio e che sono in grado di scorrere tali rappresentazioni.  
  
 Esempi di controlli che possono presentare più viste includono la visualizzazione elenco, che può mostrare il contenuto come anteprime, riquadri, icone o dettagli), grafici di Microsoft Excel (a torta, a linee, a barre, valore della cella con una formula), documenti di Microsoft Word (normale, layout Web, layout di stampa, layout di lettura, struttura), calendario di Microsoft Outlook (anno, mese, settimana, giorno) e interfacce di Media Player di Microsoft Windows. Le visualizzazioni supportate sono determinate dallo sviluppatore del controllo e sono specifiche di ogni controllo.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo MultipleView, tenere presenti le linee guida e le convenzioni seguenti:  
  
- Anche l'interfaccia<xref:System.Windows.Automation.Provider.IMultipleViewProvider> deve essere implementata in un contenitore che gestisce la visualizzazione corrente se è diversa da un controllo che fornisce la visualizzazione corrente. Ad esempio, Esplora risorse contiene un controllo elenco per il contenuto della cartella corrente, mentre la visualizzazione per il controllo viene gestita dall'applicazione Esplora risorse.  
  
- Un controllo in grado di ordinare il relativo contenuto non supporta più visualizzazioni.  
  
- La raccolta di visualizzazioni deve essere identica tra istanze.  
  
- I nomi delle visualizzazioni devono essere adatti all'uso nelle applicazioni di sintesi vocale o nelle altre applicazioni per la lettura in Braille e altri metodi di lettura.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a>Membri obbligatori per IMultipleViewProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di IMultipleViewProvider.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Metodo|Nessuno|  
  
 Non sono presenti eventi associati a questo pattern di controllo.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Viene eseguita una chiamata a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parametro che non è un membro della raccolta delle visualizzazioni supportate.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Panoramica dell'albero di automazione dell'interfaccia utente](ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](use-caching-in-ui-automation.md)
