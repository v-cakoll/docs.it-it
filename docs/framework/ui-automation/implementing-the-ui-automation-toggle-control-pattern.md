---
title: Implementazione del pattern di controllo Toggle di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: a9b03fbffc4e922cb3d00738e8df00fc0393b799
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043140"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a>Implementazione del pattern di controllo Toggle di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IToggleProvider>, incluse le informazioni relative a metodi e proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.TogglePattern> viene usato per supportare i controlli che possono scorrere un insieme di stati e gestire uno stato impostato. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Toggle, tenere presenti le linee guida e le convenzioni seguenti:  
  
- I controlli che, una volta attivati, non mantengono lo stato, ad esempio pulsanti, pulsanti della barra degli strumenti e collegamenti ipertestuali, devono invece implementare <xref:System.Windows.Automation.Provider.IInvokeProvider> .  
  
- Un controllo deve scorrere i relativi <xref:System.Windows.Automation.ToggleState> nell'ordine seguente: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> e, se supportato, <xref:System.Windows.Automation.ToggleState.Indeterminate>.  
  
- <xref:System.Windows.Automation.TogglePattern> non implementa un metodo SetState(newState) a causa di problemi relativi all'impostazione diretta di una casella di controllo a tre stati senza la possibilità di scorrere la relativa sequenza <xref:System.Windows.Automation.ToggleState> appropriata.  
  
- Il controllo RadioButton non implementa <xref:System.Windows.Automation.Provider.IToggleProvider>perché non è in grado di eseguire lo scorrimento tra gli stati validi.  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a>Membri obbligatori per IToggleProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IToggleProvider>.  
  
|Membro obbligatorio|Tipo di membro|Note|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|Metodo|Nessuna|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Proprietà|Nessuna|  
  
 Questo pattern di controllo non è associato a eventi.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 Questo pattern di controllo non è associato a eccezioni.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Ottenere lo stato di attivo/non attivo di una casella di controllo usando l'automazione interfaccia utente](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [Panoramica dell'albero di automazione interfaccia utente](ui-automation-tree-overview.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](use-caching-in-ui-automation.md)
