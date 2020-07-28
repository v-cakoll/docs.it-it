---
title: Implementazione del pattern di controllo Scroll di automazione interfaccia utente
description: Esaminare le linee guida e le convenzioni per l'implementazione del pattern di controllo Scroll nell'automazione interfaccia utente. Vedere Membri obbligatori per l'interfaccia IScrollProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
ms.openlocfilehash: 830d65286f27302dcad109384b8df187ed4af1a5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166995"
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a>Implementazione del pattern di controllo Scroll di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IScrollProvider>, incluse le informazioni relative a eventi e proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.ScrollPattern> viene usato per supportare un controllo che funge da contenitore scorrevole per una raccolta di oggetti figlio. Pur supportandole, il controllo non deve usare le barre di scorrimento per supportare la funzionalità di scorrimento.  
  
 ![Controllo Scroll senza barre di scorrimento](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")  
Esempio di controllo scorrevole che non usa barre di scorrimento  
  
 Per esempi di controlli che implementano questo controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Scroll, tenere presenti le linee guida e le convenzioni seguenti:  
  
- Gli elementi figlio di questo controllo devono implementare <xref:System.Windows.Automation.Provider.IScrollItemProvider>.  
  
- Le barre di scorrimento di un controllo contenitore non supportano il pattern di controllo <xref:System.Windows.Automation.ScrollPattern> . Devono invece supportare il pattern di controllo <xref:System.Windows.Automation.RangeValuePattern> .  
  
- Quando lo scorrimento è misurato in percentuali, tutti i valori o gli importi relativi alla scala di scorrimento devono essere normalizzati in base a un intervallo compreso tra 0 e 100.  
  
- <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> e <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> sono indipendenti da <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.  
  
- Se <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` , <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> deve essere impostata su 100% e <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> deve essere impostata su <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. In modo analogo, se <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` , <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> deve essere impostata su 100% e <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> deve essere impostata su <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. In questo modo un client di automazione interfaccia utente è in grado di usare questi valori di proprietà all'interno del metodo <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> evitando una [race condition](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) se viene attivata una direzione di scorrimento non pertinente per il client.  
  
- <xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> dipende dalle impostazioni locali. L'impostazione di HorizontalScrollPercent = 100.0 deve impostare la posizione di scorrimento del controllo sull'equivalente della posizione all'estrema destra per lingue caratterizzate dalla lettura da sinistra a destra, ad esempio l'inglese. In alternativa, per lingue caratterizzate dalla lettura da destra a sinistra, ad esempio l'arabo, l'impostazione di HorizontalScrollPercent = 100.0 deve impostare la posizione di scorrimento nella posizione più a sinistra.  
  
<a name="Required_Members_for_IScrollProvider"></a>
## <a name="required-members-for-iscrollprovider"></a>Membri obbligatori per IScrollProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IScrollProvider>.  
  
|Membro obbligatorio|Tipo di membro|Note|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|Metodo|Nessuno|  
  
 Questo pattern di controllo non è associato a eventi.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> genera questa eccezione se un controllo supporta valori di <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> esclusivamente per lo scorrimento orizzontale o verticale, ma viene passato un valore di <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> .|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> genera questa eccezione quando viene passato un valore che non può essere convertito in valore double.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> genera questa eccezione quando viene passato un valore maggiore di 100 o minore di 0 (eccetto -1, che equivale a <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> e <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> generano entrambi questa eccezione quando viene effettuato un tentativo di scorrimento in una direzione non supportata.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Panoramica dell'albero di automazione dell'interfaccia utente](ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](use-caching-in-ui-automation.md)
