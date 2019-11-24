---
title: Implementazione del pattern di controllo Grid di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, grid
- grid control pattern
- UI Automation, grid control pattern
ms.assetid: 234d11a0-7ce7-4309-8989-2f4720e02f78
ms.openlocfilehash: f4b5f1763b655026b20f37605d4649606af7fea6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435369"
---
# <a name="implementing-the-ui-automation-grid-control-pattern"></a>Implementazione del pattern di controllo Grid di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IGridProvider>, incluse le informazioni relative a proprietà, metodi ed eventi. Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.GridPattern> viene usato per supportare i controlli che fungono da contenitori per una raccolta di elementi figlio. Gli elementi figlio di questo elemento devono implementare <xref:System.Windows.Automation.Provider.IGridItemProvider> e devono essere organizzati in un sistema di coordinate logico bidimensionale che può essere attraversato da righe e colonne. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Grid, tenere presenti le linee guida e le convenzioni seguenti:  
  
- Le coordinate della griglia sono in base zero, dove la cella in alto a sinistra (o in alto a destra a seconda delle impostazioni locali) ha coordinate (0, 0).  
  
- Se una cella è vuota, è necessario che venga restituito un elemento di automazione interfaccia utente per supportare la proprietà <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> per tale cella. Ciò è possibile quando il layout degli elementi figlio nella griglia è simile a una matrice irregolare (vedere l'esempio riportato di seguito).  
  
 ![Windows Explorer view showing ragged layout.](./media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")  
Esempio di controllo griglia con coordinate vuote  
  
- Una griglia contenente un singolo elemento deve comunque implementare <xref:System.Windows.Automation.Provider.IGridProvider> se viene logicamente considerata una griglia. Il numero di elementi figlio nella griglia non ha importanza.  
  
- Le righe e colonne nascoste, a seconda dell'implementazione del provider, possono essere caricate nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e pertanto influenzare le proprietà <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> e <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> . Se le righe e colonne nascoste non sono ancora state caricate, non devono essere contate.  
  
- <xref:System.Windows.Automation.Provider.IGridProvider> non consente la modifica attiva di una griglia. <xref:System.Windows.Automation.Provider.ITransformProvider> deve essere implementata per abilitare questa funzionalità.  
  
- Usare un'interfaccia <xref:System.Windows.Automation.StructureChangedEventHandler> per attendere le modifiche strutturali o di layout della griglia, ad esempio l'aggiunta, la rimozione o l'unione di celle.  
  
- Usare un'interfaccia <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> per registrare l'attraversamento di elementi o celle di una griglia.  
  
<a name="Required_Members_for_IGridProvider"></a>   
## <a name="required-members-for-igridprovider"></a>Membri obbligatori per IGridProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione dell'interfaccia IGridProvider.  
  
|Membri obbligatori|Digitare|Note|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A>|proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>|proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A>|Metodo|Nessuno|  
  
 Questo pattern di controllo non è associato a eventi.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> -   If the requested row coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> or the column coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> -   If either of the requested row or column coordinates is less than zero.|  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Implementazione del pattern di controllo GridItem di automazione interfaccia utente](implementing-the-ui-automation-griditem-control-pattern.md)
- [Panoramica dell'albero di automazione interfaccia utente](ui-automation-tree-overview.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](use-caching-in-ui-automation.md)
