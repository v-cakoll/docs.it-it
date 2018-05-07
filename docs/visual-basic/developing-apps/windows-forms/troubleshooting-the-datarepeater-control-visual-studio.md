---
title: Risoluzione dei problemi relativi al controllo DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 092bbe89bb73a40dee7161f014d40a581b0ddc06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Risoluzione dei problemi relativi al controllo DataRepeater (Visual Studio)
In questo argomento vengono elencati i problemi che possono verificarsi quando si lavora con la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>DataRepeater tastiera e Mouse eventi non vengono generati.  
 Alcuni <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> eventi di controllo, ad esempio gli eventi di tastiera e mouse, non vengono generati. Si tratta di un comportamento correlato alla progettazione. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo stesso è un contenitore per <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> oggetti e non è accessibile in fase di esecuzione. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> non espone eventi in fase di progettazione. Pertanto, fare clic su un elemento o un tasto quando l'elemento ha lo stato attivo non genera un evento.  
  
 L'eccezione è quando il <xref:System.Windows.Forms.Control.Padding%2A> proprietà è impostata su un grande valore abbastanza per esporre i bordi del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. In questo caso, fare clic sul margine esposto genererà gli eventi del mouse.  
  
 Per risolvere questo problema, aggiungere un <xref:System.Windows.Forms.Panel> controllo il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> sezione del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllare e quindi aggiungere il resto dei controlli per il <xref:System.Windows.Forms.Panel>. È quindi possibile aggiungere codice per il <xref:System.Windows.Forms.Panel> gestori eventi per gli eventi di tastiera e mouse.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>DataRepeater parzialmente nascosto dietro il controllo BindingNavigator  
 Quando si aggiunge un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> il controllo a un form e quindi aggiungere i controlli con associazione a dati il **origini dati** finestra il <xref:System.Windows.Forms.BindingNavigator> controllo apparire in cima il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Si tratta di una limitazione nota del **origini dati** finestra ed è coerente con il comportamento di altri controlli, ad esempio il <xref:System.Windows.Forms.DataGridView> controllo.  
  
 È possibile spostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> inferiore di <xref:System.Windows.Forms.BindingNavigator> controllo in fase di progettazione o aggiungere codice simile a quanto segue nel `Load` gestore dell'evento.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Controlli non vengono visualizzati correttamente in fase di esecuzione  
 Alcuni controlli in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo potrebbe non essere visualizzato come previsto in fase di esecuzione. Il processo utilizzato per duplicare i controlli dal <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> sempre non è possibile determinare tutte le proprietà di tutti i controlli. Ad esempio, se si aggiunge un oggetto non associato <xref:System.Windows.Forms.ListBox> il controllo a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di progettazione e popola la <xref:System.Windows.Forms.ListBox.Items%2A> insieme con un elenco di stringhe, il <xref:System.Windows.Forms.ListBox> sarà vuoto in fase di esecuzione. In questo modo il processo di clonazione non è possibile prendere in considerazione la <xref:System.Windows.Forms.ListBox.Items%2A> proprietà.  
  
 Per risolvere problemi come questo ripristinando le proprietà mancanti nella <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> evento che si verifica al termine della duplicazione predefinita. Nell'esempio riportato di seguito viene illustrato come ripristinare il <xref:System.Windows.Forms.ListBox.Items%2A> raccolta di un <xref:System.Windows.Forms.ListBox> controllo il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> gestore dell'evento.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Manca il simbolo di selezione nell'intestazione dell'elemento  
 Quando si modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> proprietà dell'intestazione dell'elemento in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> (controllo), alcune opzioni colore potrebbe essere il simbolo di selezione venga rimosso. Modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà potrebbe causare anche il simbolo di selezione venga rimosso.  
  
 Impossibile modificare il colore e dimensioni del simbolo della selezione.  
  
-   Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non saranno visibile quando un elemento è selezionato prima.  
  
-   Se si imposta la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.Black%2A>, il simbolo di selezione non saranno visibile quando si seleziona un controllo e il simbolo della matita non saranno visibile quando un controllo è in modalità di modifica.  
  
-   Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
 È possibile fornire il proprio simbolo di intestazione e la selezione di elemento utilizzando un <xref:System.Windows.Forms.PictureBox> di controllo e monitoraggio di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> proprietà del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> evento del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare il layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: Disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [Procedura: Cercare dati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
