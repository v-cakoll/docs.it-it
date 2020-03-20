---
title: Implementazione del pattern di controllo Transform di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: 5643bc85972ea33cc31b1a83ecf7615dbb275bc2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180044"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a>Implementazione del pattern di controllo Transform di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.ITransformProvider>, incluse le informazioni relative a proprietà, metodi ed eventi. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.TransformPattern> viene usato per supportare i controlli che possono essere spostati, ridimensionati o ruotati in uno spazio bidimensionale. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Transform, tenere presenti le linee guida e le convenzioni seguenti:  
  
- Il supporto per questo pattern di controllo non è limitato agli oggetti sul desktop. Questo pattern di controllo deve essere supportato dagli elementi figlio di un oggetto contenitore se gli elementi figlio possono essere spostati, ridimensionati o ruotati all'interno dei limiti del contenitore.  
  
- Un oggetto non può essere spostato, ridimensionato o ruotato in modo che la posizione risultante sullo schermo potrebbe essere completamente esterna alle coordinate del relativo contenitore e pertanto inaccessibile per la tastiera o il mouse (ad esempio, quando una finestra di primo livello viene spostata fuori schermo o un oggetto figlio viene spostato fuori dai limiti del riquadro di visualizzazione del contenitore). In questi casi, l'oggetto viene posizionato il più vicino possibile alle coordinate richieste dello schermo rispetto alle coordinate in alto e a sinistra entro i limiti del contenitore.  
  
- Per sistemi con più monitor, se un oggetto viene spostato, ridimensionato o ruotato completamente al di fuori delle coordinate combinate dello schermo desktop, l'oggetto viene posizionato sul monitor principale il più vicino possibile alle coordinate richieste.  
  
- Tutti i parametri e i valori delle proprietà sono assoluti e indipendenti dalle impostazioni locali.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-itransformprovider"></a>Membri obbligatori per ITransformProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.ITransformProvider>.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|Metodo|nessuno|  
  
 Questo pattern di controllo non è associato a eventi.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> - Se <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> l'è falso.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> - Se <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> l'è falso.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> - Se <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> l'è falso.|  
  
## <a name="see-also"></a>Vedere anche

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](use-caching-in-ui-automation.md)
