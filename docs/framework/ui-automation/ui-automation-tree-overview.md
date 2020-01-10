---
title: Panoramica dell'albero di automazione dell'interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
ms.openlocfilehash: f541aab7ed5aae48b943ba5699366fe6a3f21a4c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741387"
---
# <a name="ui-automation-tree-overview"></a>Panoramica dell'albero di automazione dell'interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Prodotti e script di test di assistive technology esplorano l'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per raccogliere informazioni sull'[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e i relativi elementi.  
  
 All'interno dell'albero [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] è presente un elemento radice (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>) che rappresenta il desktop corrente e i cui elementi figlio rappresentano le finestre dell'applicazione. Ognuno di questi elemento figlio può contenere elementi che rappresentano parti dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], ad esempio menu, pulsanti, barre degli strumenti e caselle di riepilogo. Tali elementi, a loro volta, possono contenere altri elementi, ad esempio voci di elenco.  
  
 L'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non è una struttura fissa e viene visualizzata raramente in modo completo perché potrebbe contenere migliaia di elementi. Parti dell'albero vengono compilate in base alle esigenze e la struttura può subire modifiche man mano che vengono aggiunti, spostati o rimossi elementi.  
  
 I provider di automazione interfaccia utente supportano l'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] mediante l'implementazione dello spostamento tra gli elementi all'interno di un frammento, costituito da una radice (generalmente ospitata in una finestra) e un sottoalbero. I provider, tuttavia, non sono interessati dallo spostamento da un controllo a un altro. Questa operazione è gestita dagli elementi di base di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], mediante informazioni fornite dai provider di finestra predefiniti.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Visualizzazioni dell'albero di automazione  
 L'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] può essere filtrato per creare visualizzazioni che contengono solo gli oggetti <xref:System.Windows.Automation.AutomationElement> rilevanti per un determinato client. Questo approccio consente ai client di personalizzare la struttura presentata tramite [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] in base a esigenze specifiche.  
  
 Il client consente di personalizzare la visualizzazione in due modi: tramite ambito e tramite filtro. L'ambito consiste nel definire l'estensione della visualizzazione, a partire da un elemento di base. Ad esempio, è possibile che l'applicazione cerchi solo i figli diretti del desktop o tutti i discendenti di una finestra dell'applicazione. Il filtro consiste nel definire i tipi di elementi da includere nella visualizzazione.  
  
 I provider di automazione interfaccia utente supportano i filtri mediante la definizione di proprietà sugli elementi, incluse le proprietà <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> e <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] offre tre visualizzazioni predefinite, che sono definite dal tipo di filtro eseguito. L'ambito di qualsiasi visualizzazione è definito dall'applicazione. L'applicazione può inoltre applicare altri filtri sulle proprietà, ad esempio per includere solo i controlli abilitati in una visualizzazione controlli.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Visualizzazione non elaborata  
 La visualizzazione non elaborata dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] è l'albero completo degli oggetti <xref:System.Windows.Automation.AutomationElement> di cui il desktop è la radice. La visualizzazione non elaborata riproduce la struttura a livello di codice nativa di un'applicazione ed è pertanto la visualizzazione più dettagliata disponibile. Costituisce inoltre la base sulla quale vengono compilate le altre visualizzazioni dell'albero. Poiché questa vista dipende dal Framework [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] sottostante, la visualizzazione non elaborata di un pulsante [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] avrà una visualizzazione non elaborata diversa da quella di un pulsante Win32.  
  
 La visualizzazione non elaborata si ottiene cercando elementi senza specificare proprietà o usando <xref:System.Windows.Automation.TreeWalker.RawViewWalker> per esplorare l'albero.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Visualizzazione controlli  
 Le attività di descrizione dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] e di assistenza all'utente finale nell'interazione con l'applicazione eseguite dal prodotto di assistive technology vengono semplificate dalla visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], che mappa la struttura dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] percepita da un utente finale.  
  
 La visualizzazione controlli è un sottoinsieme della visualizzazione non elaborata. Include tutti gli elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] della visualizzazione non elaborata che un utente finale potrebbe considerare interattivi o inerenti la struttura logica del controllo nell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Alcuni esempi di elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] che contribuiscono alla struttura logica dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], senza essere interattivi, sono i contenitori dell'elemento quali le intestazioni della visualizzazione elenco, le barre degli strumenti, i menu e la barra di stato. Gli elementi non interattivi usati semplicemente a scopi di layout o decorativi non saranno presenti nella visualizzazione controlli. Ne è un esempio un pannello usato solo per il layout di controlli in una finestra di dialogo che non contiene alcuna informazione. Gli elementi non interattivi presenti nella visualizzazione controlli sono grafici con informazioni e testo statico in una finestra di dialogo. Gli elementi non interattivi inclusi nella visualizzazione controlli non possono ricevere lo stato attivo della tastiera.  
  
 La visualizzazione controlli si ottiene cercando elementi con la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> impostata su `true` o usando <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> per esplorare l'albero.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Visualizzazione contenuto  
 La visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] è un sottoinsieme della visualizzazione controlli. Contiene gli elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] che contengono le informazioni effettive in un'interfaccia utente, inclusi gli elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] che possono ricevere lo stato attivo della tastiera e il testo che non è un'etichetta in un elemento dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Ad esempio, i valori in una casella combinata a discesa saranno presenti nella visualizzazione contenuto poiché rappresentano le informazioni usate da un utente finale. Nella visualizzazione contenuto, una casella combinata e una casella di riepilogo sono entrambe rappresentate come un insieme di elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in cui è possibile selezionare uno o più elementi. Il fatto che un elemento sia sempre aperto e un altro possa essere espanso o compresso è irrilevante nella visualizzazione contenuto, che è progettata per mostrare i dati, o il contenuto, presentato all'utente.  
  
 La visualizzazione contenuto si ottiene cercando elementi con la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> impostata su `true` o usando <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> per esplorare l'albero.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.AutomationElement>
- [Panoramica di automazione interfaccia utente](ui-automation-overview.md)
