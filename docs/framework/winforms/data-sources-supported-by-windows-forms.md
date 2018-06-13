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
ms.openlocfilehash: 4705c8a7153e94fa1cd23cf6c2f622d5cd66ec77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541177"
---
# <a name="data-sources-supported-by-windows-forms"></a>Origini dati supportate da Windows Form
In genere, l'associazione dati è stato utilizzato all'interno delle applicazioni di sfruttare i dati archiviati nei database. Con l'associazione di dati di Windows Form, è possibile accedere ai dati dal database, nonché i dati in altre strutture, ad esempio matrici e raccolte, purché siano stati soddisfatti determinati requisiti minimi.  
  
## <a name="structures-to-bind-to"></a>Strutture a cui associare  
 In Windows Form, è possibile associare a un'ampia gamma di strutture, da semplici oggetti (associazione semplice) agli elenchi complessi, ad esempio tabelle di dati ADO.NET (associazione complessa). Per l'associazione semplice, Windows Form supporta l'associazione per le proprietà pubbliche per l'oggetto semplice. Binding in Windows Form basato su elenchi, in genere richiede che l'oggetto supporta la <xref:System.Collections.IList> interfaccia o <xref:System.ComponentModel.IListSource> interfaccia. Inoltre, se si desidera associare con tramite un <xref:System.Windows.Forms.BindingSource> componente, è possibile associare a un oggetto che supporta il <xref:System.Collections.IEnumerable> interfaccia. Per ulteriori informazioni sulle interfacce correlate al data binding, vedere [interfacce correlate al Data Binding](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 L'elenco seguente mostra le strutture, che è possibile associare a in Windows Form.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Oggetto <xref:System.Windows.Forms.BindingSource> è l'origine di dati più comune di Windows Form e agisce come proxy tra un'origine dati e i controlli Windows Form. Generale <xref:System.Windows.Forms.BindingSource> modello di utilizzo consiste nell'associare i controlli per il <xref:System.Windows.Forms.BindingSource> e associare il <xref:System.Windows.Forms.BindingSource> all'origine dati (ad esempio, una tabella di dati ADO.NET o un oggetto business). Il <xref:System.Windows.Forms.BindingSource> offre servizi che attiva e migliorano il livello di supporto dell'associazione dati. Ad esempio, Windows Form controlli basati su elenchi, ad esempio il <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.ComboBox> non supportano direttamente l'associazione a <xref:System.Collections.IEnumerable> origini dati, tuttavia, è possibile abilitare questo scenario creando un'associazione mediante un <xref:System.Windows.Forms.BindingSource>. In questo caso, il <xref:System.Windows.Forms.BindingSource> convertirà l'origine dati per un <xref:System.Collections.IList>.  
  
 Oggetti semplici  
 Windows Form supporta la proprietà del controllo di associazione dati a proprietà pubbliche nell'istanza di un oggetto utilizzando il <xref:System.Windows.Forms.Binding> tipo. Windows Form supporta anche controlli basati su elenchi di associazione, ad esempio un <xref:System.Windows.Forms.ListControl> a un oggetto istanza quando un <xref:System.Windows.Forms.BindingSource> viene utilizzato.  
  
 matrice o raccolta  
 Per funzionare come un'origine dati, è necessario implementare un elenco di <xref:System.Collections.IList> interfaccia, una esempio sarebbe una matrice che rappresenta un'istanza del <xref:System.Array> classe. Per ulteriori informazioni sulle matrici, vedere [procedura: creare una matrice di oggetti (Visual Basic)](http://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 In generale, è necessario utilizzare <xref:System.ComponentModel.BindingList%601> quando si crea l'elenco di oggetti per l'associazione dati. <xref:System.ComponentModel.BindingList%601> è una versione generica del <xref:System.ComponentModel.IBindingList> interfaccia. Il <xref:System.ComponentModel.IBindingList> interfaccia estende il <xref:System.Collections.IList> interfaccia tramite l'aggiunta di proprietà, metodi ed eventi necessari per l'associazione dati bidirezionale.  
  
 <xref:System.Collections.IEnumerable>  
 Controlli Windows Form possono essere associati a origini dati che supportano solo il <xref:System.Collections.IEnumerable> interfaccia se vengono associati tramite una <xref:System.Windows.Forms.BindingSource> componente.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] oggetti dati  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] fornisce una serie di strutture di dati adatte per l'associazione. Ogni varia la complessità e la complessità.  
  
-   <xref:System.Data.DataColumn>. Oggetto <xref:System.Data.DataColumn> è il blocco predefinito fondamentale di un <xref:System.Data.DataTable>, in quanto un numero di colonne costituita una tabella. Ogni <xref:System.Data.DataColumn> ha un <xref:System.Data.DataColumn.DataType%2A> proprietà che determina il tipo di dati contenuti nelle colonne (ad esempio, il di un'automobile in una tabella che descrive un'automobile). È possibile semplice associare un controllo (ad esempio un <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.Control.Text%2A> proprietà) a una colonna all'interno di una tabella di dati.  
  
-   <xref:System.Data.DataTable>. Oggetto <xref:System.Data.DataTable> è la rappresentazione di una tabella con righe e colonne, in [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Una tabella di dati contiene due raccolte: <xref:System.Data.DataColumn>, che rappresenta le colonne di dati in una tabella specificata (che determinano i tipi di dati che possono essere inseriti in tale tabella), e <xref:System.Data.DataRow>, che rappresenta le righe di dati in una tabella specificata. È possibile complesso connettere un controllo per le informazioni contenute in una tabella di dati (ad esempio l'associazione di <xref:System.Windows.Forms.DataGridView> controllo a una tabella di dati). Tuttavia, quando si associa a un <xref:System.Data.DataTable>, si è in realtà un'associazione alla visualizzazione predefinita della tabella.  
  
-   <xref:System.Data.DataView>. Oggetto <xref:System.Data.DataView> è una visualizzazione personalizzata di un'unica tabella dati che può essere ordinata o filtrata. Una vista dati è i dati utilizzati dai controlli con associazione complessa "snapshot". È possibile associazione semplice o complesso per i dati all'interno di una visualizzazione dati, ma è tenere presente che si desidera associare a un' "immagine" predefinita dei dati anziché a un'origine dati viene aggiornata.  
  
-   <xref:System.Data.DataSet>. Oggetto <xref:System.Data.DataSet> è una raccolta di tabelle, relazioni e vincoli dei dati in un database. È possibile un'associazione semplice o complesso per i dati all'interno di un set di dati, ma è tenere presente che si associa il valore predefinito <xref:System.Data.DataViewManager> per il <xref:System.Data.DataSet> (come illustrato al successivo punto).  
  
-   <xref:System.Data.DataViewManager>. A <xref:System.Data.DataViewManager> è una visualizzazione personalizzata dell'intero <xref:System.Data.DataSet>, analogo a un <xref:System.Data.DataView>, ma con relazioni. Con un <xref:System.Data.DataViewManager.DataViewSettings%2A> insieme, è possibile impostare i filtri predefiniti e opzioni di ordinamento per tutte le viste che il <xref:System.Data.DataViewManager> per una determinata tabella.  
  
## <a name="see-also"></a>Vedere anche  
 [Notifica delle modifiche nel data binding dei Windows Form](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Data binding e Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Data binding in Windows Form](../../../docs/framework/winforms/windows-forms-data-binding.md)
