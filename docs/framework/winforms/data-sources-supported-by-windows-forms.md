---
title: Origini dati supportate
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: 83ce4bb0d6f0bf81bcad4e38af212dccc3483ca5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742304"
---
# <a name="data-sources-supported-by-windows-forms"></a>Origini dati supportate da Windows Form
Tradizionalmente, data binding è stato utilizzato all'interno delle applicazioni per sfruttare i dati archiviati nei database di. Con Windows Forms data binding, è possibile accedere ai dati da database, nonché dati in altre strutture, ad esempio matrici e raccolte, a condizione che siano stati soddisfatti determinati requisiti minimi.  
  
## <a name="structures-to-bind-to"></a>Strutture da associare  
 In Windows Forms, è possibile eseguire l'associazione a un'ampia gamma di strutture, da semplici oggetti (associazione semplice) a elenchi complessi, ad esempio tabelle di dati ADO.NET (Binding complesso). Per l'associazione semplice, Windows Forms supporta l'associazione alle proprietà pubbliche nell'oggetto semplice. Windows Forms associazione basata su elenco richiede in genere che l'oggetto supporti l'interfaccia <xref:System.Collections.IList> o l'interfaccia <xref:System.ComponentModel.IListSource>. Inoltre, se si esegue il binding con tramite un componente di <xref:System.Windows.Forms.BindingSource>, è possibile eseguire l'associazione a un oggetto che supporta l'interfaccia <xref:System.Collections.IEnumerable>. Per ulteriori informazioni sulle interfacce correlate ai data binding, vedere [interfacce correlate all'associazione dati](interfaces-related-to-data-binding.md).  
  
 Nell'elenco seguente vengono illustrate le strutture a cui è possibile eseguire il binding in Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Un <xref:System.Windows.Forms.BindingSource> è l'origine dati Windows Forms più comune e funge da proxy tra un'origine dati e controlli di Windows Forms. Il modello di utilizzo generale <xref:System.Windows.Forms.BindingSource> consiste nell'associare i controlli al <xref:System.Windows.Forms.BindingSource> e associare il <xref:System.Windows.Forms.BindingSource> all'origine dati, ad esempio una tabella di dati ADO.NET o un oggetto business. Il <xref:System.Windows.Forms.BindingSource> fornisce servizi che abilitano e migliorano il livello di supporto data binding. Ad esempio, Windows Forms controlli basati su elenco come <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.ComboBox> non supportano direttamente l'associazione a <xref:System.Collections.IEnumerable> origini dati, tuttavia, è possibile abilitare questo scenario associando un <xref:System.Windows.Forms.BindingSource>. In questo caso, il <xref:System.Windows.Forms.BindingSource> convertirà l'origine dati in una <xref:System.Collections.IList>.  
  
 Oggetti semplici  
 Windows Forms supporta data binding proprietà del controllo per le proprietà pubbliche nell'istanza di un oggetto utilizzando il tipo di <xref:System.Windows.Forms.Binding>. Windows Forms supporta anche i controlli basati su elenco di binding, ad esempio un <xref:System.Windows.Forms.ListControl> a un'istanza dell'oggetto quando viene utilizzata una <xref:System.Windows.Forms.BindingSource>.  
  
 matrice o raccolta  
 Per fungere da origine dati, un elenco deve implementare l'interfaccia <xref:System.Collections.IList>; un esempio è costituito da una matrice che rappresenta un'istanza della classe <xref:System.Array>. Per ulteriori informazioni sulle matrici, vedere [procedura: creare una matrice di oggetti (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 In generale, è consigliabile usare <xref:System.ComponentModel.BindingList%601> quando si creano elenchi di oggetti per data binding. <xref:System.ComponentModel.BindingList%601> è una versione generica dell'interfaccia <xref:System.ComponentModel.IBindingList>. L'interfaccia <xref:System.ComponentModel.IBindingList> estende l'interfaccia <xref:System.Collections.IList> aggiungendo proprietà, metodi ed eventi necessari per data binding bidirezionale.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms i controlli possono essere associati a origini dati che supportano solo l'interfaccia <xref:System.Collections.IEnumerable> se sono associate tramite un componente <xref:System.Windows.Forms.BindingSource>.  
  
 Oggetti dati ADO.NET  
 ADO.NET fornisce una serie di strutture di dati adatte per l'associazione a. Ognuno di essi varia in base alla complessità e alla complessità.  
  
- <xref:System.Data.DataColumn> Un <xref:System.Data.DataColumn> è il blocco predefinito essenziale di un <xref:System.Data.DataTable>, in quanto un numero di colonne comprende una tabella. Ogni <xref:System.Data.DataColumn> dispone di una proprietà <xref:System.Data.DataColumn.DataType%2A> che determina il tipo di dati contenuti nella colonna (ad esempio, la marca di un'automobile in una tabella che descrive le automobili). È possibile associare in modo semplice un controllo, ad esempio una proprietà <xref:System.Windows.Forms.Control.Text%2A> di un controllo <xref:System.Windows.Forms.TextBox>, a una colonna all'interno di una tabella di dati.  
  
- <xref:System.Data.DataTable> Una <xref:System.Data.DataTable> è la rappresentazione di una tabella, con righe e colonne, in ADO.NET. Una tabella di dati contiene due raccolte: <xref:System.Data.DataColumn>, che rappresentano le colonne di dati in una determinata tabella, che in definitiva determinano i tipi di dati che possono essere immessi in tale tabella, e <xref:System.Data.DataRow>, che rappresentano le righe di dati in una tabella specificata. È possibile associare in modo complesso un controllo alle informazioni contenute in una tabella dati, ad esempio l'associazione del controllo <xref:System.Windows.Forms.DataGridView> a una tabella di dati. Tuttavia, quando si esegue l'associazione a una <xref:System.Data.DataTable>, si è effettivamente associati alla visualizzazione predefinita della tabella.  
  
- <xref:System.Data.DataView> Una <xref:System.Data.DataView> è una visualizzazione personalizzata di una singola tabella dati che può essere filtrata o ordinata. Una vista dati è il "snapshot" dei dati usato da controlli con associazione complessa. È possibile eseguire un'associazione semplice o complessa ai dati all'interno di una visualizzazione dati, ma tenere presente che si sta eseguendo il binding a una "immagine" fissa dei dati piuttosto che a un'origine dati pulita e aggiornabile.  
  
- <xref:System.Data.DataSet> Un <xref:System.Data.DataSet> è una raccolta di tabelle, relazioni e vincoli dei dati in un database di. È possibile associare in modo semplice o complesso i dati all'interno di un set di dati, ma tenere presente che si sta associando al <xref:System.Data.DataViewManager> predefinito per il <xref:System.Data.DataSet> (vedere il punto di puntamento successivo).  
  
- <xref:System.Data.DataViewManager> Una <xref:System.Data.DataViewManager> è una visualizzazione personalizzata dell'intera <xref:System.Data.DataSet>, analoga a una <xref:System.Data.DataView>, ma con le relazioni incluse. Con una raccolta di <xref:System.Data.DataViewManager.DataViewSettings%2A>, è possibile impostare filtri e opzioni di ordinamento predefiniti per tutte le visualizzazioni che il <xref:System.Data.DataViewManager> ha per una determinata tabella.  
  
## <a name="see-also"></a>Vedere anche

- [Notifica delle modifiche nel data binding dei Windows Form](change-notification-in-windows-forms-data-binding.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
- [Associazione ai dati di Windows Form](windows-forms-data-binding.md)
