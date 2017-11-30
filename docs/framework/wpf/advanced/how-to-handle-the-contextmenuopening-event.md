---
title: 'Procedura: gestire l''evento ContextMenuOpening'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61048a8db67986c55e1a1b07d62d5142069dd63e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Procedura: gestire l'evento ContextMenuOpening
Il <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento può essere gestito in un'applicazione per modificare un contesto menu esistente prima di visualizzare o eliminare il menu che sarebbe altrimenti visualizzato impostando il <xref:System.Windows.RoutedEventArgs.Handled%2A> proprietà `true` nei dati dell'evento. La ragione più comune per l'impostazione <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` dati dell'evento consiste nella sostituzione menu interamente con un nuovo <xref:System.Windows.Controls.ContextMenu> dell'oggetto, che talvolta richiede l'annullamento dell'operazione e avviare una nuova apertura. Se si scrivono i gestori per il <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento, è necessario essere consapevoli dei problemi di temporizzazione tra un <xref:System.Windows.Controls.ContextMenu> controllo e il servizio è responsabile dell'apertura e la posizione del menu di scelta rapida per i controlli in generale. In questo argomento vengono illustrate alcune delle tecniche di codice per diversi menu di scelta rapida aprire scenari e viene illustrato un caso in cui il problema di temporizzazione entra in gioco.  
  
 Esistono diversi scenari per la gestione di <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento:  
  
-   Modificare le voci di menu prima della visualizzazione.  
  
-   Sostituire l'intero menu prima della visualizzazione.  
  
-   Completamente l'eliminazione di qualsiasi menu di scelta rapida esistente e la visualizzazione non menu di scelta rapida.  
  
## <a name="example"></a>Esempio  
  
## <a name="adjusting-the-menu-items-before-display"></a>Modificare le voci di Menu prima della visualizzazione  
 La regolazione delle voci di menu esistenti è piuttosto semplice e probabilmente lo scenario più comune. È possibile farlo per poter aggiungere o sottrarre opzioni del menu contestuale in risposta alle informazioni sullo stato corrente dell'applicazione o informazioni sullo stato determinato che sono disponibile come proprietà nell'oggetto in cui è richiesto il menu di scelta rapida.  
  
 La tecnica generale consiste nell'ottenere l'origine dell'evento, ovvero il controllo specifico selezionato, il <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà da esso. In genere si desidera controllare il <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme per visualizzare le voci del menu contestuale già esiste nel menu e quindi aggiungere o rimuovere new appropriato <xref:System.Windows.Controls.MenuItem> elementi a o dalla raccolta.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Sostituire l'intero Menu prima della visualizzazione  
 Uno scenario alternativo è se si desidera sostituire il menu contestuale intero. Naturalmente è possibile utilizzare anche una variante dell'esempio precedente, rimuovere tutti gli elementi di un menu di scelta rapida esistente e aggiungerne di nuovi, iniziando dall'elemento zero. Ma è l'approccio più intuitivo per sostituire tutte le voci di menu di scelta rapida per creare un nuovo <xref:System.Windows.Controls.ContextMenu>viene popolato con gli elementi e quindi impostare il <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> proprietà di un controllo che sarà il nuovo <xref:System.Windows.Controls.ContextMenu>.  
  
 Ecco il codice del gestore semplice per la sostituzione di un <xref:System.Windows.Controls.ContextMenu>. Il codice fa riferimento a un oggetto personalizzato `BuildMenu` metodo separato perché viene chiamato da più di uno dei gestori di esempio.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Tuttavia, se si utilizza questo stile di gestore per <xref:System.Windows.FrameworkElement.ContextMenuOpening>, è possibile esporre un problema di temporizzazione potenzialmente se l'oggetto a cui si sta impostando il <xref:System.Windows.Controls.ContextMenu> non dispone di un menu di scelta rapida preesistente. Quando un utente fa un controllo, <xref:System.Windows.FrameworkElement.ContextMenuOpening> viene generato anche se l'oggetto esistente <xref:System.Windows.Controls.ContextMenu> è vuoto o null. Ma in questo caso, qualsiasi nuovo <xref:System.Windows.Controls.ContextMenu> è impostata sull'origine elemento arriva troppo tardi per poter essere visualizzati. Inoltre, se l'utente a fare doppio clic su una seconda volta, questa volta, il nuovo <xref:System.Windows.Controls.ContextMenu> visualizzata, il valore è non null e il gestore correttamente sostituirà e visualizzare il menu quando il gestore esegue una seconda volta. Ciò suggerisce due possibili soluzioni:  
  
1.  Assicurare che <xref:System.Windows.FrameworkElement.ContextMenuOpening> gestori sempre eseguiti in controlli che dispongono di almeno un segnaposto <xref:System.Windows.Controls.ContextMenu> disponibili, che si desidera essere sostituito con il codice del gestore. In questo caso, è comunque possibile utilizzare il gestore mostrato nell'esempio precedente, ma in genere si desidera assegnare un segnaposto <xref:System.Windows.Controls.ContextMenu> nel markup iniziale:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Si supponga che iniziale <xref:System.Windows.Controls.ContextMenu> valore potrebbe essere null, in base a logica preliminare. È possibile archiviarla <xref:System.Windows.Controls.ContextMenu> è null o utilizzare un flag nel codice per verificare se il gestore è stato eseguito almeno una volta. Poiché è presupporre che il <xref:System.Windows.Controls.ContextMenu> sta per essere visualizzato, il gestore, quindi imposta <xref:System.Windows.RoutedEventArgs.Handled%2A> per `true` nei dati dell'evento. Per il <xref:System.Windows.Controls.ContextMenuService> responsabile per la visualizzazione del menu contesto, un `true` valore per <xref:System.Windows.RoutedEventArgs.Handled%2A> nell'evento dati rappresentano una richiesta per annullare la visualizzazione per il menu di scelta rapida della combinazione / controllo che ha generato l'evento.  
  
 Dopo aver eliminato il menu contestuale potenzialmente sospetti, il passaggio successivo consiste nel fornire uno nuovo, quindi visualizzarlo. L'impostazione di un nuovo menu è fondamentalmente lo stesso gestore precedente: si crea un nuovo <xref:System.Windows.Controls.ContextMenu> e impostare l'origine di controllo <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> proprietà con esso. Il passaggio aggiuntivo è che ora è necessario forzare la visualizzazione del menu di scelta rapida, perché è stata eliminata al primo tentativo. Per forzare la visualizzazione, impostare il <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> proprietà `true` all'interno del gestore. Prestare attenzione quando si esegue questa operazione, poiché aprendo il menu di scelta rapida nel gestore genera il <xref:System.Windows.FrameworkElement.ContextMenuOpening> nuovo evento. Se si accede nuovamente al gestore, diventa all'infinito ricorsiva. È per questo motivo è sempre necessario verificare la presenza di `null` o utilizzare un flag, se si apre un menu di scelta rapida dall'interno un <xref:System.Windows.FrameworkElement.ContextMenuOpening> gestore dell'evento.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Eliminazione di qualsiasi menu di scelta rapida esistente e la visualizzazione di alcun menu di scelta rapida  
 Nello scenario finale, scrivere un gestore che elimina completamente, un menu è comune. Se un determinato controllo non deve per visualizzare un menu di scelta rapida, sono disponibili modi più appropriati per assicurare che questa rispetto all'eliminazione del menu solo quando un utente lo richiede. Se si desidera utilizzare il gestore per eliminare un menu di scelta rapida senza visualizzare nulla, allora il gestore deve semplicemente impostare <xref:System.Windows.RoutedEventArgs.Handled%2A> per `true` nei dati dell'evento. Il <xref:System.Windows.Controls.ContextMenuService> che è responsabile della visualizzazione di un menu di scelta rapida controllerà i dati dell'evento dell'evento generato sul controllo. Se l'evento è stato contrassegnato come <xref:System.Windows.RoutedEventArgs.Handled%2A> in qualsiasi punto della route, quindi l'azione scelta rapida aprire che ha avviato l'evento è eliminata.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [Cenni preliminari sugli elementi di base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Panoramica sull'oggetto ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
