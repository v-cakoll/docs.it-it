---
title: Origini dati supportate da Windows Form
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
ms.openlocfilehash: aee15d8d40ddd3f928c8bc5396d8bcbff17ba533
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858912"
---
# <a name="data-sources-supported-by-windows-forms"></a>Origini dati supportate da Windows Form
In genere, l'associazione dati è stata utilizzata all'interno delle applicazioni per sfruttare i vantaggi dei dati archiviati nel database. Con data binding in Windows Form, è possibile accedere ai dati dal database, nonché i dati in altre strutture, ad esempio matrici e raccolte, purché siano stati soddisfatti alcuni requisiti minimi.  
  
## <a name="structures-to-bind-to"></a>Strutture a cui associare  
 In Windows Form, è possibile associare a un'ampia gamma di strutture, da semplici oggetti (associazione semplice) agli elenchi complessi, ad esempio tabelle di dati ADO.NET (associazione complessa). Per l'associazione semplice, Windows Forms supporta l'associazione a proprietà pubbliche per l'oggetto semplice. Binding basato su elenchi in Windows Form in genere richiede che l'oggetto supporta la <xref:System.Collections.IList> interfaccia o <xref:System.ComponentModel.IListSource> interfaccia. Inoltre, se si desidera associare con tramite una <xref:System.Windows.Forms.BindingSource> componente, è possibile associare a un oggetto che supporta il <xref:System.Collections.IEnumerable> interfaccia. Per altre informazioni sulle interfacce correlate al data binding, vedere [interfacce correlate al Data Binding](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 L'elenco seguente illustra le strutture, che è possibile associare a in Windows Form.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Oggetto <xref:System.Windows.Forms.BindingSource> è l'origine dati di Windows Form più comune e agisce come proxy tra un'origine dati e controlli Windows Form. Generali <xref:System.Windows.Forms.BindingSource> modello di utilizzo consiste nell'associare i controlli per il <xref:System.Windows.Forms.BindingSource> ed eseguire l'associazione di <xref:System.Windows.Forms.BindingSource> all'origine dati (ad esempio, una tabella di dati di ADO.NET o un oggetto business). Il <xref:System.Windows.Forms.BindingSource> fornisce servizi che abilitano e migliorano il livello di supporto dell'associazione dati. Ad esempio, Windows Form controlli basati su elenchi, ad esempio la <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.ComboBox> non supportano direttamente l'associazione al <xref:System.Collections.IEnumerable> origini dati, tuttavia, è possibile abilitare questo scenario creando un'associazione tramite un <xref:System.Windows.Forms.BindingSource>. In questo caso, il <xref:System.Windows.Forms.BindingSource> convertirà l'origine dati da un <xref:System.Collections.IList>.  
  
 Oggetti semplici  
 Windows Forms supporta proprietà di controllo data binding a proprietà pubbliche nell'istanza di un oggetto tramite il <xref:System.Windows.Forms.Binding> tipo. Windows Forms supporta anche controlli basati su elenchi di associazione, ad esempio un <xref:System.Windows.Forms.ListControl> a un oggetto istanza quando un <xref:System.Windows.Forms.BindingSource> viene usato.  
  
 matrice o raccolta  
 Per eseguire operazioni come origine dati, è necessario implementare un elenco di <xref:System.Collections.IList> interfaccia, una esempio sarebbe una matrice che è un'istanza del <xref:System.Array> classe. Per altre informazioni sulle matrici, vedere [procedura: creare una matrice di oggetti (Visual Basic)](https://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 In generale, è consigliabile usare <xref:System.ComponentModel.BindingList%601> quando si creano elenchi di oggetti per il data binding. <xref:System.ComponentModel.BindingList%601> è una versione generica del <xref:System.ComponentModel.IBindingList> interfaccia. Il <xref:System.ComponentModel.IBindingList> interfaccia estende il <xref:System.Collections.IList> interfaccia mediante l'aggiunta di proprietà, metodi ed eventi necessari per l'associazione dati bidirezionale.  
  
 <xref:System.Collections.IEnumerable>  
 Controlli Windows Form possono essere associati alle origini dati che supportano solo il <xref:System.Collections.IEnumerable> interfaccia se vengono associati attraverso un <xref:System.Windows.Forms.BindingSource> componente.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] oggetti dati  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] fornisce una serie di strutture di dati adatte per l'associazione. Ciascuna offre il livello di complessità e la complessità.  
  
-   <xref:System.Data.DataColumn>. Oggetto <xref:System.Data.DataColumn> è il blocco predefinito fondamentale di un <xref:System.Data.DataTable>, in quanto un numero di colonne costituita una tabella. Ciascuna <xref:System.Data.DataColumn> ha un <xref:System.Data.DataColumn.DataType%2A> proprietà che determina il tipo di dati contenuti nelle colonne (ad esempio, i componenti di un'automobile in una tabella che descrive automobili). È possibile semplice associare un controllo (ad esempio un <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà) a una colonna all'interno di una tabella di dati.  
  
-   <xref:System.Data.DataTable>. Oggetto <xref:System.Data.DataTable> è la rappresentazione di una tabella con righe e colonne, in [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Una tabella di dati contiene due raccolte: <xref:System.Data.DataColumn>, che rappresenta le colonne di dati in una determinata tabella (che viene determinato il tipo di dati che possono essere immessi nella tabella), e <xref:System.Data.DataRow>, che rappresenta le righe di dati in una determinata tabella. È possibile complesso associare un controllo per le informazioni contenute in una tabella di dati (ad esempio l'associazione di <xref:System.Windows.Forms.DataGridView> controllo a una tabella dati). Tuttavia, quando si associa a un <xref:System.Data.DataTable>, si è in realtà un'associazione alla visualizzazione predefinita della tabella.  
  
-   <xref:System.Data.DataView>. Oggetto <xref:System.Data.DataView> è una visualizzazione personalizzata di una singola tabella dati che può essere ordinata o filtrata. Una vista dati è i dati "snapshot" utilizzato dai controlli con associazione complessa. È possibile un'associazione semplice o complesso per i dati all'interno di una vista dati, ma è essere a conoscenza che si desidera associare a un' "immagine" fissa dei dati anziché un'origine dati viene aggiornata.  
  
-   <xref:System.Data.DataSet>. Oggetto <xref:System.Data.DataSet> è una raccolta di tabelle, relazioni e vincoli dei dati in un database. È possibile eseguire un'associazione semplice o complesso per i dati all'interno di un set di dati, ma è tenere presente che si associa il valore predefinito <xref:System.Data.DataViewManager> per il <xref:System.Data.DataSet> (come indicato al successivo punto).  
  
-   <xref:System.Data.DataViewManager>. Oggetto <xref:System.Data.DataViewManager> è una visualizzazione personalizzata dell'intera <xref:System.Data.DataSet>, analogo a un <xref:System.Data.DataView>, ma con le relazioni inclusione. Con un <xref:System.Data.DataViewManager.DataViewSettings%2A> raccolta, è possibile impostare i filtri predefiniti e le opzioni di ordinamento per tutte le viste che il <xref:System.Data.DataViewManager> per una determinata tabella.  
  
## <a name="see-also"></a>Vedere anche  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
