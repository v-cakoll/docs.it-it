---
title: Utilizzo di automazione interfaccia utente per il test automatico
description: Leggere una panoramica che descrive come usare l'automazione dell'interfaccia utente come Framework per l'accesso a livello di codice in scenari di test automatici.
ms.date: 03/30/2017
helpviewer_keywords:
- automated testing
- testing, UI Automation
- UI Automation, automated testing
ms.assetid: 3a0435c0-a791-4ad7-ba92-a4c1d1231fde
ms.openlocfilehash: a38efd30e6f7f4cd05664d847c525dcf59ded61a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924474"
---
# <a name="using-ui-automation-for-automated-testing"></a>Utilizzo di automazione interfaccia utente per il test automatico
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questa panoramica viene descritta l'utilità di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] come framework per l'accesso a livello di codice in scenari di test automatici.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] fornisce un modello a oggetti unificato che consente a tutti i framework dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] di esporre funzionalità complesse e dettagliate in modo accessibile e automatico.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]è stato sviluppato come successore di Microsoft Active Accessibility. Active Accessibility è un Framework esistente progettato per offrire una soluzione per rendere accessibili controlli e applicazioni. Active Accessibility non è stato progettato tenendo conto dell'automazione di test anche se si è evoluto in questo ruolo a causa dei requisiti molto simili di accessibilità e automazione. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], oltre a offrire soluzioni ottimali per l'accessibilità, è progettato appositamente per fornire funzionalità affidabili di test automatici. Ad esempio, Active Accessibility si basa su una singola interfaccia per esporre informazioni sull'interfaccia utente e raccogliere le informazioni necessarie per i prodotti; [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]separa i due modelli.  
  
 Sono necessari un provider e un client per implementare [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] affinché risulti utile come strumento di test automatizzato. I provider di automazione interfaccia utente sono applicazioni come Microsoft Word, Excel e altre applicazioni di terze parti o controlli basati sul sistema operativo Microsoft Windows. I client di automazione interfaccia utente includono script di test automatizzati e applicazioni di assistive technology.  
  
> [!NOTE]
> Lo scopo di questa panoramica consiste nel presentare le funzionalità di test automatizzati nuove e migliorate disponibili in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. In questa panoramica non verranno fornite informazioni sulle funzionalità di accessibilità, concetto che verrà trattato solo quando necessario.  
  
## <a name="ui-automation-in-a-provider"></a>Automazione interfaccia utente in un provider  
 Per automatizzare un' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , è necessario che lo sviluppatore di un'applicazione o di un controllo esamini quali azioni possono essere eseguite da un utente finale sull'oggetto [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mediante l'interazione di una tastiera e un mouse standard.  
  
 Una volta individuate queste azioni chiave, è necessario implementare sul controllo i pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] corrispondenti, ovvero i pattern di controllo che riflettono le funzionalità e il comportamento dell'elemento dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Ad esempio, l'interazione dell'utente con un controllo casella combinata (ad esempio, la finestra di dialogo Esegui) prevede in genere l'espansione e la compressione della casella combinata per nascondere o visualizzare un elenco di elementi, la selezione di un elemento dall'elenco o l'aggiunta di un nuovo valore tramite input della tastiera.  
  
> [!NOTE]
> Con altri modelli di accessibilità, è necessario che gli sviluppatori raccolgano le informazioni direttamente da singoli pulsanti, menu o altri controlli. Ogni tipo di controllo, purtroppo, è disponibile in decine di varianti minori. In altre parole, anche se dieci varianti di un pulsante possono funzionare tutte allo stesso modo ed eseguire la stessa funzione, devono essere trattate come controlli univoci. Non è possibile sapere se tali controlli sono equivalenti a livello funzionale. I pattern di controllo sono stati sviluppati per rappresentare questi comportamenti comuni dei controlli. Per altre informazioni, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
### <a name="implementing-ui-automation"></a>Implementazione di automazione interfaccia utente  
 Come indicato in precedenza, senza il modello unificato fornito da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], è necessario che strumenti di test e sviluppatori conoscano le informazioni specifiche del framework per esporre proprietà e comportamenti dei controlli in tale framework. Poiché possono essere presenti diversi framework dell'interfaccia utente in qualsiasi momento all'interno dei sistemi operativi Windows, tra cui Win32, Windows Forms e Windows Presentation Foundation (WPF), può essere un'attività ardua testare più applicazioni con controlli simili. Nella tabella seguente, ad esempio, sono indicati i nomi delle proprietà specifiche del framework richieste per recuperare il nome (o il testo) associato a un controllo pulsante e viene riportata la singola proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] equivalente.  
  
|Tipo di controllo di automazione interfaccia utente|Framework di interfaccia utente|Proprietà specifica del framework|Proprietà di automazione interfaccia utente|  
|--------------------------------|------------------|---------------------------------|----------------------------|  
|Pulsante|Windows Presentation Foundation|Content|NameProperty|  
|Pulsante|Win32|Sottotitolo|NameProperty|  
|Immagine|HTML|alt|NameProperty|  
  
 I provider di automazione interfaccia utente sono responsabili dell'esecuzione del mapping delle proprietà specifiche del framework dei controlli alle proprietà equivalenti di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Per informazioni sull'implementazione di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] in un provider, vedere [UI Automation Providers for Managed Code](ui-automation-providers-for-managed-code.md). Per informazioni sull'implementazione di pattern di controllo, vedere [UI Automation Control Patterns](ui-automation-control-patterns.md) e [UI Automation Text Pattern](ui-automation-text-pattern.md).  
  
## <a name="ui-automation-in-a-client"></a>Automazione interfaccia utente in un client  
 L'obiettivo di molti strumenti e scenari di test automatizzati è la modifica coerente e ripetibile dell'interfaccia utente, che può comportare controlli specifici di unit test e la registrazione e la riproduzione di script di test che ripetono una serie di azioni generiche su un gruppo di controlli.  
  
 Una complicazione legata alle applicazioni automatiche è la difficoltà della sincronizzazione di un test con una destinazione dinamica. Ad esempio, un controllo casella di riepilogo, quale un controllo contenuto in Gestione attività Windows, che visualizza un elenco di applicazioni attualmente in esecuzione. Poiché gli elementi nella casella di riepilogo sono aggiornati dinamicamente all'esterno del controllo dell'applicazione di test, è impossibile tentare di ripetere la selezione di un elemento specifico nella casella di riepilogo in modo coerente. Problemi analoghi possono sorgere anche quando si tenta di ripetere semplici modifiche dello stato attivo in un' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] esterna al controllo dell'applicazione di test.  
  
### <a name="programmatic-access"></a>Accesso a livello di codice  
 L'accesso a livello di codice consente di imitare, tramite codice, qualsiasi interazione ed esperienza esposta dall'input tradizionale di mouse e tastiera. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] consente l'accesso a livello di codice tramite cinque componenti:  
  
- L'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] facilita la navigazione nella struttura dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. L'albero è compilato dalla raccolta di hWnd. Per altre informazioni, vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
- Gli elementi di automazione sono singoli componenti dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] e sono spesso più granulari di un hWnd. Per altre informazioni, vedere [UI Automation Control Types Overview](ui-automation-control-types-overview.md).  
  
- Le proprietà di automazione forniscono informazioni specifiche sugli elementi dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Per altre informazioni, vedere [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
- I pattern di controllo definiscono un determinato aspetto della funzionalità di un controllo e possono essere costituiti da informazioni di proprietà, metodo, evento e struttura. Per altre informazioni, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
- Gli eventi di automazione forniscono notifiche e informazioni sugli eventi. Per altre informazioni, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
### <a name="key-properties-for-test-automation"></a>Proprietà chiave per l'automazione di test  
 La possibilità di identificare in modo univoco e di trovare successivamente qualsiasi controllo all'interno dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] è la base per il funzionamento delle applicazioni di test automatizzate su tale [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Le proprietà di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] usate da client e provider utili a questo scopo sono numerose.  
  
#### <a name="automationid"></a>AutomationID  
 Identifica in modo univoco un elemento di automazione da elementi di pari livello. <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> non è localizzato, a differenza di una proprietà come <xref:System.Windows.Automation.AutomationElement.NameProperty> che in genere è localizzata se un prodotto viene fornito in più lingue. Vedere [Use the AutomationID Property](use-the-automationid-property.md).  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> non garantisce un'identità univoca in tutto l'albero di automazione. Ad esempio, un'applicazione può contenere un controllo menu con più voci di menu di livello superiore che, a loro volta, contengono più voci di menu figlio. Queste voci di menu secondarie possono essere identificate da uno schema generico, ad esempio "Item1, Item2, Item3 e così via", consentendo identificatori duplicati per i figli tra voci di menu di livello superiore.  
  
#### <a name="controltype"></a>ControlType  
 Identifica il tipo di controllo rappresentato da un elemento di automazione. La conoscenza del tipo di controllo consente di acquisire informazioni significative. Vedere [UI Automation Control Types Overview](ui-automation-control-types-overview.md).  
  
#### <a name="nameproperty"></a>NameProperty  
 Si tratta di una stringa di testo che identifica o spiega un controllo. È necessario usare<xref:System.Windows.Automation.AutomationElement.NameProperty> con attenzione in quanto può essere localizzato. Vedere [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
### <a name="implementing-ui-automation-in-a-test-application"></a>Implementazione di automazione interfaccia utente in un'applicazione di test  
  
|||  
|-|-|  
|Aggiungere i riferimenti di automazione interfaccia utente.|Le DLL di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necessarie per i client di automazione interfaccia utente sono elencate di seguito.<br /><br /> -UIAutomationClient.dll fornisce l'accesso alle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API lato client.<br />-UIAutomationClientSideProvider.dll fornisce la possibilità di automatizzare i controlli Win32. Vedere [UI Automation Support for Standard Controls](ui-automation-support-for-standard-controls.md).<br />-UIAutomationTypes.dll consente di accedere ai tipi specifici definiti in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|Aggiungere lo spazio dei nomi <xref:System.Windows.Automation> .|Questo spazio dei nomi contiene tutti gli elementi necessari ai client di automazione interfaccia utente per usare le funzionalità di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , tranne la gestione del testo.|  
|Aggiungere lo spazio dei nomi <xref:System.Windows.Automation.Text> .|Questo spazio dei nomi contiene tutti gli elementi necessari ai client di automazione interfaccia utente per usare le funzionalità di gestione di testo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|Individuare i controlli di interesse.|Gli script di test automatizzati consentono di individuare gli elementi di automazione interfaccia utente che rappresentano controlli di interesse all'interno dell'albero di automazione.<br /><br /> È possibile ottenere elementi di automazione interfaccia utente con il codice in diversi modi.<br /><br /> -Eseguire una query su [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] usando un' <xref:System.Windows.Automation.Condition> istruzione. In questo caso, viene in genere usato il campo <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> indipendente dalla lingua. **Nota:**  <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>È possibile ottenere un oggetto usando uno strumento come Inspect.exe in grado di descrivere le [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà di un controllo. <br /><br /> -Usare la <xref:System.Windows.Automation.TreeWalker> classe per attraversare l'intero [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] albero o un sottoinsieme.<br />-Tenere traccia dello stato attivo.<br />-Usare hWnd del controllo.<br />-Utilizzare la posizione dello schermo, ad esempio la posizione del cursore del mouse.<br /><br /> Vedere [Obtaining UI Automation Elements](obtaining-ui-automation-elements.md)|  
|Ottenere i pattern di controllo.|I pattern di controllo espongono comportamenti comuni per controlli simili a livello funzionale.<br /><br /> Dopo aver individuato i controlli che richiedono test, gli script di test automatizzati ottengono i pattern di controllo di interesse da tali elementi di automazione interfaccia utente. Ad esempio, il pattern di controllo <xref:System.Windows.Automation.InvokePattern> per la tipica funzionalità di pulsante o il pattern di controllo <xref:System.Windows.Automation.WindowPattern> per la funzionalità di finestra.<br /><br /> Vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).|  
|Automatizzare l'interfaccia utente.|È ora possibile usare script di test automatizzati per controllare qualsiasi [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] di interesse da un framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] usando informazioni e funzionalità esposte dai pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
## <a name="related-tools-and-technologies"></a>Strumenti e tecnologie correlati  
 Sono disponibili vari strumenti e tecnologie correlati che supportano i test automatizzati con [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
- Inspect.exe è un'applicazione GUI (Graphical User Interface) che può essere usata per raccogliere [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] informazioni per lo sviluppo e il debug di provider e client. Inspect.exe è incluso nel Windows SDK.  
  
- MSAABridge espone [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] le informazioni ai client Active Accessibility. L'obiettivo principale del bridging [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Active Accessibility consiste nel consentire ai client Active Accessibility esistenti di interagire con qualsiasi framework implementato [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
## <a name="security"></a>Sicurezza  
 Per informazioni sulla sicurezza, vedere [UI Automation Security Overview](ui-automation-security-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'automazione interfaccia utente](index.md)
