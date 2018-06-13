---
title: Controlli con supporto incorporato per la creazione da parte del proprietario
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: a5cbdc733a2f1cda3e708ceaae8604297f8da58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529247"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Controlli con supporto incorporato per la creazione da parte del proprietario
Il disegno da parte del proprietario in Windows Form, noto anche come disegno personalizzato, è una tecnica che consente di modificare l'aspetto visivo di alcuni controlli.  
  
> [!NOTE]
>  La parola "controllo" in questo argomento viene utilizzata per indicare le classi che derivano da <xref:System.Windows.Forms.Control> o <xref:System.ComponentModel.Component>.  
  
 In genere, Windows gestisce il disegno automaticamente utilizzando le impostazioni delle proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColor%2A> per determinare l'aspetto di un controllo. Con il disegno da parte del proprietario, si acquisisce la precedenza sul processo di disegno, modificando elementi dell'aspetto non disponibili quando si usano le proprietà. Molti controlli, ad esempio, consentono di impostare il colore del testo visualizzato, ma è previsto un limite di un solo colore. Il disegno da parte del proprietario consente, ad esempio, di visualizzare parte del testo in nero e parte in rosso.  
  
 Il disegno da parte del proprietario è in pratica simile al disegno di elementi grafici in un form. Ad esempio, è possibile utilizzare i metodi grafici in un gestore per il form <xref:System.Windows.Forms.Control.Paint> evento per emulare un `ListBox` controllo, ma è necessario scrivere codice personalizzato per gestire tutte le interazioni utente. Con il disegno da parte del proprietario, il controllo usa il codice per disegnare i contenuti, ma mantiene tutte le funzionalità intrinseche. È possibile usare metodi Graphics per disegnare ogni elemento nel controllo o per personalizzare alcuni dettagli di ogni elemento mentre si usa l'aspetto predefinito per altri dettagli di ogni elemento.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Disegno da parte del proprietario nei controlli Windows Form  
 Per eseguire il disegno da parte del proprietario nei controlli che lo supportano, in genere è necessario impostare una proprietà e gestire uno o più eventi.  
  
 La maggior parte dei controlli che supportano il disegno da parte del proprietario ha una proprietà `OwnerDraw` o `DrawMode` che indica se il controllo genera uno o più eventi correlati al disegno quando disegna se stesso.  
  
 I controlli senza la proprietà `OwnerDraw` o `DrawMode` includono il controllo `DataGridView`, che fornisce eventi di disegno che si verificano automaticamente, e il controllo `ToolStrip`, che viene disegnato usando una classe di rendering esterna con i propri eventi correlati al disegno.  
  
 Sono disponibili molti tipi di eventi di disegno diversi, ma un evento di disegno tipico si verifica per disegnare un singolo elemento in un controllo. Il gestore eventi riceve un oggetto `EventArgs` che contiene informazioni sull'elemento che viene disegnato e sugli strumenti che è possibile usare per disegnarlo. Ad esempio, l'oggetto contiene in genere il numero di indice dell'elemento all'interno della raccolta padre, un <xref:System.Drawing.Rectangle> che indica i limiti di visualizzazione dell'elemento e un <xref:System.Drawing.Graphics> oggetto per la chiamata di metodi di disegno. Per alcuni eventi, l'oggetto `EventArgs` fornisce informazioni aggiuntive sull'elemento e sui metodi che è possibile chiamare per disegnare alcuni dettagli dell'elemento per impostazione predefinita, ad esempio lo sfondo o il rettangolo dello stato attivo.  
  
 Per creare un controllo riutilizzabile contenente le personalizzazioni disegnate dal proprietario, creare una nuova classe che deriva da una classe di controlli che supporta il disegno da parte del proprietario. Invece di gestire gli eventi di disegno, includere il codice del disegno da parte del proprietario negli override per uno o più metodi `On`*EventName* appropriati nella nuova classe. In questo caso, verificare di chiamare il metodo o i metodi `On`*EventName* della classe base in modo che gli utenti del controllo possano gestire gli eventi di disegno da parte del proprietario e creare personalizzazioni aggiuntive.  
  
 I controlli Windows Form seguenti supportano il disegno da parte del proprietario in tutte le versioni di .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem> (utilizzato da <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 I controlli seguenti supportano il disegno da parte del proprietario solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 I controlli seguenti, che supportano il disegno da parte del proprietario, sono nuovi in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Le sezioni seguenti contengono altre informazioni dettagliate su ogni controllo.  
  
### <a name="listbox-and-combobox-controls"></a>Controlli ListBox e ComboBox  
 Il <xref:System.Windows.Forms.ListBox> e <xref:System.Windows.Forms.ComboBox> controlli consentono di disegnare singoli elementi nel controllo stessa dimensione o dimensioni variabili.  
  
> [!NOTE]
>  Sebbene il <xref:System.Windows.Forms.CheckedListBox> controllo derivato dal <xref:System.Windows.Forms.ListBox> (controllo), non supporta il disegno personalizzato.  
  
 Per disegnare ogni elemento con la stessa dimensione, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> e gestire il `DrawItem` evento.  
  
 Per disegnare ogni elemento con dimensioni diverse, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> e gestire entrambi i `MeasureItem` e `DrawItem` eventi. L'evento `MeasureItem` consente di indicare le dimensioni di un elemento prima che si verifichi l'evento `DrawItem` per tale elemento.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [Procedura: Creare testo di dimensioni variabili in un controllo ComboBox](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Componente MenuItem  
 Il <xref:System.Windows.Forms.MenuItem> componente rappresenta una singola voce di menu in un <xref:System.Windows.Forms.MainMenu> o <xref:System.Windows.Forms.ContextMenu> componente.  
  
 Per disegnare un <xref:System.Windows.Forms.MenuItem>, impostare il relativo `OwnerDraw` proprietà `true` e gestire relativo `DrawItem` evento. Per personalizzare le dimensioni della voce di menu prima che si verifichi l'evento `DrawItem`, gestire l'evento `MeasureItem` dell'elemento.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>Controllo TabControl  
 Il <xref:System.Windows.Forms.TabControl> controllo consente di disegnare singole schede nel controllo. Il disegno personalizzato influisce solo sulle schede. il <xref:System.Windows.Forms.TabPage> non subiscono alcun contenuto.  
  
 Per disegnare ogni scheda in un <xref:System.Windows.Forms.TabControl>, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> e gestire il `DrawItem` evento. Questo evento si verifica una volta per ogni scheda solo quando la scheda è visibile nel controllo.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>Componente ToolTip  
 Il <xref:System.Windows.Forms.ToolTip> componente consente di disegnare la descrizione comandi quando viene visualizzato.  
  
 Per disegnare un <xref:System.Windows.Forms.ToolTip>, impostare il relativo `OwnerDraw` proprietà `true` e gestire relativo `Draw` evento. Per personalizzare le dimensioni del <xref:System.Windows.Forms.ToolTip> prima il `Draw` si verifica l'evento, gestire il `Popup` evento e impostare il <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> proprietà nel gestore eventi.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>Controllo ListView  
 Il <xref:System.Windows.Forms.ListView> controllo consente di disegnare singoli elementi, gli elementi secondari e le intestazioni di colonna nel controllo.  
  
 Per abilitare il disegno da parte del proprietario nel controllo, impostare la proprietà `OwnerDraw` su `true`.  
  
 Per disegnare ogni elemento nel controllo, gestire l'evento `DrawItem`.  
  
 Per disegnare ogni intestazione dell'elemento secondario o di colonna nel controllo quando il <xref:System.Windows.Forms.ListView.View%2A> è impostata su <xref:System.Windows.Forms.View.Details>, gestire il `DrawSubItem` e `DrawColumnHeader` eventi.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>Controllo TreeView  
 Il <xref:System.Windows.Forms.TreeView> controllo consente di disegnare singoli nodi nel controllo.  
  
 Per disegnare solo il testo da visualizzare in ogni nodo, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> e gestire il `DrawNode` disegnare il testo dell'evento.  
  
 Per disegnare tutti gli elementi di ogni nodo, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> e gestire il `DrawNode` evento necessari, ad esempio testo, icone, caselle di controllo, segni più e meno e linee che collegano i nodi.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>Controllo DataGridView  
 Il <xref:System.Windows.Forms.DataGridView> controllo consente di disegnare singole celle e righe nel controllo.  
  
 Per disegnare singole celle, gestire l'evento `CellPainting`.  
  
 Per disegnare singole righe o elementi delle righe, gestire uno o entrambi gli eventi `RowPrePaint` e `RowPostPaint`. L'evento `RowPrePaint` si verifica prima che le celle in una riga vengano disegnate e l'evento `RowPostPaint` si verifica dopo che le celle sono state disegnate. È possibile gestire entrambi gli eventi e l'evento `CellPainting` per disegnare separatamente lo sfondo delle righe, le singole celle e il primo piano delle righe oppure è possibile fornire personalizzazioni specifiche ove necessario e usare la visualizzazione predefinita per gli altri elementi della riga.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>Controllo ToolStrip  
 <xref:System.Windows.Forms.ToolStrip> e i controlli derivati consentono di personalizzare qualsiasi altro aspetto relativo a come appaiono.  
  
 Per fornire per il rendering personalizzate per <xref:System.Windows.Forms.ToolStrip> i controlli, impostare il `Renderer` proprietà di un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, o <xref:System.Windows.Forms.ToolStripContentPanel> per un `ToolStripRenderer` dell'oggetto e gestire uno o più dei numerosi eventi di disegno forniti dal `ToolStripRenderer` classe. In alternativa, impostare un `Renderer` proprietà a un'istanza della classe personalizzata derivata da `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, o <xref:System.Windows.Forms.ToolStripSystemRenderer> che implementa o si esegue l'override specifico `On` *EventName* metodi.  
  
 Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Procedura: Eseguire un disegno personalizzato di un controllo ToolStrip](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
