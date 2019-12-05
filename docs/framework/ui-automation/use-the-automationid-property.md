---
title: Utilizzare la proprietà AutomationID
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutomationId property
- UI Automation, AutomationId property
- properties, AutomationId
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
ms.openlocfilehash: 43a67a8dd73931172a6fa729c054ad494b29134e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800309"
---
# <a name="use-the-automationid-property"></a>Utilizzare la proprietà AutomationID
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento contiene gli scenari e il codice di esempio che illustrano come e quando sia possibile usare <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> per individuare un elemento nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> identifica in modo univoco un elemento di automazione interfaccia utente dagli elementi di pari livello. Per altre informazioni sugli identificatori di proprietà correlati all'identificazione dei controlli, vedere [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> non garantisce un'identità univoca in tutto l'albero. Per essere utile, richiede in genere informazioni sui contenitori e sull'ambito. Ad esempio, un'applicazione può contenere un controllo menu con più voci di menu di livello superiore che, a loro volta, contengono più voci di menu figlio. Queste voci di menu secondarie possono essere identificate da uno schema generico, ad esempio "Item1", "Item 2" e così via, consentendo la presenza di identificatori duplicati per gli elementi figlio nelle voci di menu di primo livello.  
  
## <a name="scenarios"></a>Scenari  
 Sono stati identificati tre scenari principali dell'applicazione client di automazione interfaccia utente, che richiedono l'uso di <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> per ottenere risultati accurati e coerenti quando si cercano elementi.  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> è supportato da tutti gli elementi di automazione interfaccia utente nella visualizzazione controlli tranne che dalle finestre dell'applicazione di primo livello, dagli elementi di automazione interfaccia utente derivati da controlli [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] senza ID o x:Uid e dagli elementi di automazione interfaccia utente derivati da controlli [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] senza ID controllo.  
  
#### <a name="use-a-unique-and-discoverable-automationid-to-locate-a-specific-element-in-the-ui-automation-tree"></a>Usare un oggetto AutomationID univoco e individuabile per trovare un elemento specifico nell'albero di automazione interfaccia utente  
  
- Usare uno strumento come Spy interfaccia utente per segnalare la <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> di un elemento [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] di interesse. Questo valore può quindi essere copiato e incollato in un'applicazione client, ad esempio uno script di test, per il successivo test automatizzato. Questo approccio riduce e semplifica il codice necessario per identificare e individuare un elemento in fase di esecuzione.  
  
> [!CAUTION]
> In generale, è consigliabile cercare di ottenere solo elementi figlio diretti di <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Una ricerca dei discendenti può scorrere centinaia o anche migliaia di elementi, con la possibilità che venga generato un overflow dello stack. Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### <a name="use-a-persistent-path-to-return-to-a-previously-identified-automationelement"></a>Usare un percorso persistente per tornare a un oggetto AutomationElement identificato in precedenza  
  
- Le applicazioni client, dai semplici script di test alle solide utilità di registrazione e riproduzione, potrebbero richiedere l'accesso a elementi di cui non è ancora stata creata un'istanza, ad esempio una finestra di dialogo di apertura file o una voce di menu, e che quindi non esistono nell'albero di automazione interfaccia utente. È possibile creare un'istanza di questi elementi solo riproducendo o riproducendo una sequenza specifica di azioni dell'interfaccia utente tramite l'utilizzo di proprietà di automazione interfaccia utente, ad esempio AutomationID, pattern di controllo e listener di eventi.
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### <a name="use-a-relative-path-to-return-to-a-previously-identified-automationelement"></a>Usare un percorso relativo per tornare a un oggetto AutomationElement identificato in precedenza  
  
- In alcune circostanze, poiché è garantito che AutomationID sia univoco solo tra gli elementi di pari livello, più elementi dell'albero di automazione interfaccia utente possono avere valori identici per la proprietà AutomationID. In questi casi, gli elementi possono essere identificati in modo univoco in base a un elemento padre e, se necessario, a un elemento padre del padre. Uno sviluppatore, ad esempio, potrebbe fornire una barra dei menu con più voci di menu, tutte con più voci di menu figlio, dove gli elementi figlio vengono identificati con AutomationID sequenziali, ad esempio "Item1", "Item2" e così via. Ogni voce di menu può quindi essere identificata in modo univoco dal rispettivo AutomationID insieme all'AutomationID del padre e, se necessario, del padre del padre.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>
- [Panoramica dell'albero di automazione interfaccia utente](ui-automation-tree-overview.md)
- [Trovare un elemento di automazione interfaccia utente in base a una condizione proprietà](find-a-ui-automation-element-based-on-a-property-condition.md)
