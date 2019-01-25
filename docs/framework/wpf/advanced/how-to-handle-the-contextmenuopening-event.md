---
title: "Procedura: Gestire l'evento ContextMenuOpening"
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: 794fad2708c799b9e5fb8ff1d2875648f886fdbb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655842"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Procedura: Gestire l'evento ContextMenuOpening
Il <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento può essere gestito in un'applicazione per modificare un esistente prima di menu di scelta rapida per visualizzare o eliminare il menu che verrà altrimenti visualizzato impostando il <xref:System.Windows.RoutedEventArgs.Handled%2A> proprietà `true` nei dati dell'evento. La ragione più comune per l'impostazione <xref:System.Windows.RoutedEventArgs.Handled%2A> al `true` dei dati nell'evento consiste nella sostituzione menu interamente con un nuovo <xref:System.Windows.Controls.ContextMenu> dell'oggetto, che a volte richiede l'annullamento dell'operazione e l'avvio di un nuovo open. Se si scrivono i gestori per il <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento, è necessario essere consapevoli dei problemi di temporizzazione tra un <xref:System.Windows.Controls.ContextMenu> controllo e il servizio che è responsabile dell'apertura e il posizionamento di menu di scelta rapida per i controlli in generale. In questo argomento vengono illustrate alcune delle tecniche di codice per scenari di apertura dei vari menu di scelta rapida e viene illustrato un caso in cui il problema di temporizzazione entra in gioco.  
  
 Esistono diversi scenari per la gestione di <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento:  
  
-   Modificare le voci di menu prima della visualizzazione.  
  
-   Sostituire l'intero menu prima della visualizzazione.  
  
-   Completamente l'eliminazione di qualsiasi menu di scelta rapida esistente e non visualizzare alcun menu di scelta rapida.  
  
## <a name="example"></a>Esempio  
  
## <a name="adjusting-the-menu-items-before-display"></a>Modificare le voci di Menu prima della visualizzazione  
 Modificando le voci di menu esistente è piuttosto semplice e probabilmente lo scenario più comune. È possibile farlo per poter aggiungere o sottrarre le opzioni di menu di scelta rapida in risposta alle informazioni sullo stato corrente dell'applicazione o informazioni sullo stato determinato che sono disponibile come una proprietà dell'oggetto in cui viene richiesto il menu di scelta rapida.  
  
 La tecnica generale consiste nell'ottenere l'origine dell'evento, vale a dire il controllo specifico acquisendone, e Ottieni la <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà da quest'ultimo. In genere si vuole controllare la <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme per vedere quali voci di menu di scelta rapida già esiste nel menu e quindi aggiungere o rimuovere appropriato new <xref:System.Windows.Controls.MenuItem> da o verso la raccolta di elementi.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Sostituire l'intero Menu prima della visualizzazione  
 Uno scenario alternativo è se si desidera sostituire il menu di scelta rapida intero. Naturalmente è possibile usare anche una variante del codice precedente, per rimuovere ogni elemento di un menu di scelta rapida esistente e aggiungerne di nuovi, iniziando dall'elemento zero. Ma l'approccio più intuitiva per la sostituzione di tutti gli elementi nel menu di scelta rapida consiste nel creare una nuova <xref:System.Windows.Controls.ContextMenu>viene popolato con gli elementi e quindi impostare il <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> proprietà di un controllo che sarà il nuovo <xref:System.Windows.Controls.ContextMenu>.  
  
 Di seguito è riportato il codice del gestore semplice per la sostituzione di un <xref:System.Windows.Controls.ContextMenu>. Il codice fa riferimento a un oggetto personalizzato `BuildMenu` metodo, che è separato perché viene chiamato da più di uno dei gestori di esempio.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Tuttavia, se si utilizza questo stile di visualizzazione del gestore per <xref:System.Windows.FrameworkElement.ContextMenuOpening>, si può esporre potenzialmente un problema di temporizzazione se l'oggetto in cui si sta impostando il <xref:System.Windows.Controls.ContextMenu> non dispone di un menu di scelta rapida preesistenti. Quando un utente fa clic di un controllo <xref:System.Windows.FrameworkElement.ContextMenuOpening> viene generato anche se l'oggetto esistente <xref:System.Windows.Controls.ContextMenu> è vuoto o null. Ma in questo caso, qualsiasi nuovo <xref:System.Windows.Controls.ContextMenu> è impostata sull'origine elemento arriva troppo tardi per poter essere visualizzati. Inoltre, se l'utente a fare doppio clic su una seconda volta, questa volta il nuovo <xref:System.Windows.Controls.ContextMenu> visualizzata, il valore è non null e il gestore verrà sostituire correttamente e verrà visualizzato il menu di scelta quando il gestore esegue una seconda volta. Ciò suggerisce possibili due soluzioni alternative:  
  
1.  Assicurarsi che <xref:System.Windows.FrameworkElement.ContextMenuOpening> gestori di eseguire sempre i controlli che hanno almeno un segnaposto <xref:System.Windows.Controls.ContextMenu> disponibili, che si prevede essere sostituito con il codice del gestore. In questo caso, è comunque possibile usare il gestore illustrato nell'esempio precedente, ma in genere si vuole assegnare un segnaposto <xref:System.Windows.Controls.ContextMenu> nel markup iniziale:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  Si supponga che iniziale <xref:System.Windows.Controls.ContextMenu> valore potrebbe essere null, basato su logica preliminare. È possibile archiviarla <xref:System.Windows.Controls.ContextMenu> è null o usare un flag nel codice per verificare se il gestore di è stato eseguito almeno una volta. Poiché si presuppone che il <xref:System.Windows.Controls.ContextMenu> sta per essere visualizzato, il gestore quindi imposta <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` nei dati dell'evento. Per il <xref:System.Windows.Controls.ContextMenuService> responsabile per la visualizzazione di menu di scelta rapida, una `true` value per <xref:System.Windows.RoutedEventArgs.Handled%2A> nell'evento dati rappresentano una richiesta di annullare la visualizzazione per il menu di scelta / controllo combinazione che ha generato l'evento.  
  
 Dopo aver eliminato il menu di scelta rapida potenzialmente sospetti, il passaggio successivo è fornire uno nuovo, quindi visualizzarlo. L'impostazione di nuovo uno è fondamentalmente lo stesso come il gestore precedente: si crea un nuovo <xref:System.Windows.Controls.ContextMenu> e impostare l'origine di controllo <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> proprietà con esso. Il passaggio aggiuntivo è che ora è necessario forzare la visualizzazione del menu di scelta rapida, perché è stato evitato al primo tentativo. Per forzare la visualizzazione, si imposta la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> proprietà `true` all'interno del gestore. Prestare attenzione quando si esegue questa operazione, poiché aprendo il menu di scelta rapida nel gestore genera il <xref:System.Windows.FrameworkElement.ContextMenuOpening> nuovo evento. Se si accede nuovamente al gestore, diventa infinitamente ricorsiva. Ecco perché è sempre necessario verificare la presenza `null` oppure usare un flag, se si apre un menu di scelta rapida dall'interno una <xref:System.Windows.FrameworkElement.ContextMenuOpening> gestore dell'evento.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Eliminazione di qualsiasi menu di scelta rapida esistente e non visualizzare alcun menu di scelta rapida  
 Nello scenario finale, scrivere un gestore che elimina completamente, un menu è insolito. Se un determinato controllo non deve per visualizzare un menu di scelta rapida, esistono modi probabilmente più appropriati per assicurare che questa rispetto all'eliminazione del menu solo quando un utente lo richiede. Se si desidera utilizzare il gestore per eliminare un menu di scelta rapida e non visualizzare nulla, allora il gestore di è sufficiente deve impostare <xref:System.Windows.RoutedEventArgs.Handled%2A> a `true` nei dati dell'evento. Il <xref:System.Windows.Controls.ContextMenuService> che è responsabile della visualizzazione di un menu di scelta rapida controllerà i dati dell'evento dell'evento generato sul controllo. Se l'evento è stato contrassegnato come <xref:System.Windows.RoutedEventArgs.Handled%2A> in qualsiasi punto lungo la route, quindi l'azione di Apri menu di scelta rapida che ha avviato l'evento viene eliminato.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>
- [Cenni preliminari sugli elementi di base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
- [Panoramica sull'oggetto ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
