---
title: Risoluzione dei problemi relativi al controllo DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, troubleshooting
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
ms.openlocfilehash: 7b045e1c45221cbde82c88286da8e698a763d844
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580603"
---
# <a name="troubleshooting-the-datarepeater-control-visual-studio"></a>Risoluzione dei problemi relativi al controllo DataRepeater (Visual Studio)
Questo argomento elenca i problemi comuni che possono verificarsi quando si lavora con i <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo.  
  
## <a name="datarepeater-keyboard-and-mouse-events-are-not-raised"></a>Non vengono generati gli eventi del Mouse e tastiera DataRepeater  
 Alcuni <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> eventi di controllo, ad esempio gli eventi di tastiera e mouse, non vengono generati. Si tratta di un comportamento correlato alla progettazione. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo stesso è un contenitore per <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> degli oggetti e non è accessibile in fase di esecuzione. Il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> non espone eventi in fase di progettazione. Pertanto, premere un tasto quando l'elemento ha lo stato attivo o facendo clic su un elemento non genera un evento.  
  
 L'eccezione è quando il <xref:System.Windows.Forms.Control.Padding%2A> proprietà è impostata su un grande valore abbastanza per esporre i bordi del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. In questo caso, facendo clic sul margine esposto genererà gli eventi del mouse.  
  
 Per risolvere questo problema, aggiungere un <xref:System.Windows.Forms.Panel> il controllo al <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> sezione del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo e quindi aggiungere il resto dei controlli dal <xref:System.Windows.Forms.Panel>. È quindi possibile aggiungere codice per il <xref:System.Windows.Forms.Panel> gestori di eventi del controllo per gli eventi di tastiera e mouse.  
  
## <a name="the-datarepeater-is-partially-hidden-behind-the-binding-navigator"></a>Controllo DataRepeater è parzialmente nascosta dietro il controllo BindingNavigator  
 Quando si aggiunge innanzitutto una <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> il controllo a un form e aggiungere i controlli con associazione a dati dal **Zdroje dat** finestra, il <xref:System.Windows.Forms.BindingNavigator> controllo appaia nella parte superiore del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Si tratta di una limitazione nota del **Zdroje dat** finestra ed è coerente con il comportamento di altri controlli, ad esempio il <xref:System.Windows.Forms.DataGridView> controllo.  
  
 È possibile spostare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> minore il <xref:System.Windows.Forms.BindingNavigator> controllo in fase di progettazione o aggiungere codice simile a quanto segue nel `Load` gestore dell'evento.  
  
```vb  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```csharp  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## <a name="controls-are-not-displayed-correctly-at-run-time"></a>Controlli non vengono visualizzati correttamente in fase di esecuzione  
 Alcuni controlli in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo potrebbe non essere visualizzato come previsto in fase di esecuzione. Il processo utilizzato per duplicare i controlli dal <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> sempre non può determinare tutte le proprietà di tutti i controlli. Ad esempio, se si aggiunge un oggetto non associato <xref:System.Windows.Forms.ListBox> il controllo a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo in fase di progettazione e popolare relativo <xref:System.Windows.Forms.ListBox.Items%2A> insieme con un elenco di stringhe, il <xref:System.Windows.Forms.ListBox> sarà vuoto in fase di esecuzione. Infatti, il processo di clonazione non è possibile prendere in considerazione il <xref:System.Windows.Forms.ListBox.Items%2A> proprietà.  
  
 Si possono risolvere i problemi come questo ripristinando le proprietà mancanti nella <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> evento che si verifica al termine della clonazione predefinito. L'esempio seguente illustra come ripristinare il <xref:System.Windows.Forms.ListBox.Items%2A> raccolta di un <xref:System.Windows.Forms.ListBox> controllare nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned> gestore dell'evento.  
  
 [!code-csharp[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="the-selection-symbol-on-the-item-header-is-missing"></a>Manca il simbolo di selezione nell'intestazione dell'elemento  
 Quando si modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> proprietà dell'intestazione dell'elemento in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> (controllo), alcune opzioni colore possono causare il simbolo di selezione venga rimosso. Modifica il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà potrebbe causare anche il simbolo di selezione venga rimosso.  
  
 Impossibile modificare il colore e dimensioni del simbolo della selezione.  
  
-   Se si impostano i <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.White%2A>, il simbolo di selezione non saranno visibile quando si seleziona prima un elemento.  
  
-   Se si impostano i <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> a <xref:System.Drawing.Color.Black%2A>, il simbolo di selezione non saranno visibile quando viene selezionato un controllo e il simbolo a forma di matita non saranno visibile quando un controllo è in modalità di modifica.  
  
-   Se il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> proprietà è impostata su un valore che è minore di 11, non verranno visualizzati i simboli di indicatore nell'intestazione dell'elemento.  
  
 È possibile fornire il proprio simbolo elemento di intestazione e la selezione tramite un <xref:System.Windows.Forms.PictureBox> controllo e il monitoraggio di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> proprietà del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> eventi del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controllo. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## <a name="see-also"></a>Vedere anche
- [Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Procedura: Visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Visualizzare i controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Modificare il Layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Procedura: Modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)
- [Procedura: Dati di ricerca in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)
- [Procedura: Creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
