---
title: Modalità di ordinamento delle colonne nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744189"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form
<xref:System.Windows.Forms.DataGridView> colonne hanno tre modalità di ordinamento. La modalità di ordinamento per ogni colonna viene specificata tramite la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> della colonna, che può essere impostata su uno dei valori di enumerazione <xref:System.Windows.Forms.DataGridViewColumnSortMode> seguenti.  
  
|Valore di `DataGridViewColumnSortMode`|Descrizione|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Impostazione predefinita per le colonne della casella di testo. A meno che le intestazioni di colonna non vengano utilizzate per la selezione, fare clic sull'intestazione di colonna per ordinare automaticamente il <xref:System.Windows.Forms.DataGridView> in base a questa colonna e visualizzare un glifo che indica l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Impostazione predefinita per le colonne della casella di testo non. È possibile ordinare questa colonna a livello di codice. Tuttavia, non è destinato all'ordinamento, pertanto nessuno spazio viene riservato per il glifo di ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|È possibile ordinare questa colonna a livello di codice e lo spazio è riservato per il glifo di ordinamento.|  
  
 Potrebbe essere necessario modificare la modalità di ordinamento per una colonna per la quale il valore predefinito è <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> se contiene valori che possono essere ordinati in modo significativo. Se, ad esempio, è presente una colonna di database contenente numeri che rappresentano gli Stati degli elementi, è possibile visualizzare questi numeri come icone corrispondenti associando una colonna dell'immagine alla colonna del database. È quindi possibile modificare i valori delle celle numeriche in valori di visualizzazione immagine in un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. In questo caso, l'impostazione della proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> su <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> consentirà agli utenti di ordinare la colonna. L'ordinamento automatico consentirà agli utenti di raggruppare gli elementi che hanno lo stesso stato anche se gli stati corrispondenti ai numeri non hanno una sequenza naturale. Le colonne della casella di controllo sono un altro esempio in cui l'ordinamento automatico è utile per raggruppare gli elementi nello stesso stato.  
  
 È possibile ordinare una <xref:System.Windows.Forms.DataGridView> a livello di codice in base ai valori di qualsiasi colonna o in più colonne, indipendentemente dalle impostazioni <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>. L'ordinamento a livello di codice è utile quando si desidera fornire un'interfaccia utente personalizzata per l'ordinamento o quando si desidera implementare l'ordinamento personalizzato. Fornire un'interfaccia utente di ordinamento personalizzata è utile, ad esempio, quando si imposta la modalità di selezione <xref:System.Windows.Forms.DataGridView> per abilitare la selezione dell'intestazione di colonna. In questo caso, anche se le intestazioni di colonna non possono essere utilizzate per l'ordinamento, è comunque necessario che le intestazioni visualizzino il glifo di ordinamento appropriato, quindi impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> su <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Le colonne impostate sulla modalità di ordinamento a livello di codice non visualizzano automaticamente un glifo di ordinamento. Per queste colonne, è necessario visualizzare il glifo impostando la proprietà <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>. Questa operazione è necessaria se si vuole flessibilità nell'ordinamento personalizzato. Se ad esempio si ordinano i <xref:System.Windows.Forms.DataGridView> in base a più colonne, è possibile che si desideri visualizzare più glifi di ordinamento o nessun glifo di ordinamento.  
  
 Sebbene sia possibile ordinare a livello di codice un <xref:System.Windows.Forms.DataGridView> in base a qualsiasi colonna, alcune colonne, ad esempio le colonne dei pulsanti, potrebbero non contenere valori che possono essere ordinati in modo significativo. Per queste colonne, un'impostazione della proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> di <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica che non verrà mai utilizzata per l'ordinamento, pertanto non è necessario riservare spazio nell'intestazione per il glifo di ordinamento.  
  
 Quando un <xref:System.Windows.Forms.DataGridView> viene ordinato, è possibile determinare la colonna di ordinamento e l'ordinamento controllando i valori delle proprietà <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A>. Questi valori non sono significativi dopo un'operazione di ordinamento personalizzata. Per ulteriori informazioni sull'ordinamento personalizzato, vedere la sezione ordinamento personalizzato più avanti in questo argomento.  
  
 Quando viene ordinato un controllo <xref:System.Windows.Forms.DataGridView> contenente le colonne con binding e non associato, i valori nelle colonne non vincolate non possono essere mantenuti automaticamente. Per mantenere questi valori, è necessario implementare la modalità virtuale impostando la proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> su `true` e gestendo gli eventi di <xref:System.Windows.Forms.DataGridView.CellValueNeeded> e <xref:System.Windows.Forms.DataGridView.CellValuePushed>. Per altre informazioni, vedere [procedura: implementare la modalità virtuale nel controllo DataGridView Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). L'ordinamento in base a colonne non vincolate in modalità di associazione non è supportato.  
  
## <a name="programmatic-sorting"></a>Ordinamento a livello di codice  
 È possibile ordinare una <xref:System.Windows.Forms.DataGridView> a livello di codice chiamando il relativo metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>.  
  
 Il `Sort(DataGridViewColumn,ListSortDirection)` overload del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> accetta un <xref:System.Windows.Forms.DataGridViewColumn> e un valore di enumerazione <xref:System.ComponentModel.ListSortDirection> come parametri. Questo overload è utile quando si esegue l'ordinamento in base a colonne con valori che possono essere ordinati in modo significativo, ma che non si desidera configurare per l'ordinamento automatico. Quando si chiama questo overload e si passa una colonna con un valore <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> della proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, le proprietà <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A> vengono impostate automaticamente e nell'intestazione di colonna viene visualizzato il glifo di ordinamento appropriato.  
  
> [!NOTE]
> Quando il controllo <xref:System.Windows.Forms.DataGridView> viene associato a un'origine dati esterna impostando la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>, l'overload del metodo `Sort(DataGridViewColumn,ListSortDirection)` non funziona per le colonne non in associazione. Inoltre, quando la proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è `true`, è possibile chiamare questo overload solo per le colonne con binding. Per determinare se una colonna è associata a dati, controllare il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>. L'ordinamento delle colonne non vincolate in modalità di associazione non è supportato.  
  
## <a name="custom-sorting"></a>Ordinamento personalizzato  
 È possibile personalizzare <xref:System.Windows.Forms.DataGridView> usando l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A> o gestendo l'evento <xref:System.Windows.Forms.DataGridView.SortCompare>.  
  
 L'overload del metodo `Sort(IComparer)` accetta un'istanza di una classe che implementa l'interfaccia <xref:System.Collections.IComparer> come parametro. Questo overload è utile quando si desidera fornire l'ordinamento personalizzato; ad esempio, quando i valori di una colonna non hanno un ordinamento naturale o quando l'ordinamento naturale non è appropriato. In questo caso, non è possibile usare l'ordinamento automatico, ma è comunque possibile che gli utenti vengano ordinati facendo clic sulle intestazioni di colonna. È possibile chiamare questo overload in un gestore per l'evento <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> se non si utilizzano le intestazioni di colonna per la selezione.  
  
> [!NOTE]
> L'overload del metodo `Sort(IComparer)` funziona solo quando il controllo <xref:System.Windows.Forms.DataGridView> non è associato a un'origine dati esterna e il valore della proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è `false`. Per personalizzare l'ordinamento delle colonne associato a un'origine dati esterna, è necessario utilizzare le operazioni di ordinamento fornite dall'origine dati. In modalità virtuale è necessario fornire le proprie operazioni di ordinamento per le colonne non in associazione.  
  
 Per usare l'overload del metodo `Sort(IComparer)`, è necessario creare una classe personalizzata che implementi l'interfaccia <xref:System.Collections.IComparer>. Questa interfaccia richiede che la classe implementi il metodo <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>, a cui il <xref:System.Windows.Forms.DataGridView> passa <xref:System.Windows.Forms.DataGridViewRow> oggetti come input quando viene chiamato l'overload del metodo `Sort(IComparer)`. In questo modo è possibile calcolare l'ordinamento corretto delle righe in base ai valori di qualsiasi colonna.  
  
 L'overload del metodo `Sort(IComparer)` non imposta le proprietà <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A>, pertanto è necessario impostare sempre la proprietà <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> per visualizzare il glifo di ordinamento.  
  
 In alternativa all'overload del metodo `Sort(IComparer)`, è possibile fornire l'ordinamento personalizzato implementando un gestore per l'evento <xref:System.Windows.Forms.DataGridView.SortCompare>. Questo evento si verifica quando gli utenti fanno clic sulle intestazioni delle colonne configurate per l'ordinamento automatico o quando si chiama l'overload `Sort(DataGridViewColumn,ListSortDirection)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>. L'evento si verifica per ogni coppia di righe nel controllo, consentendo di calcolare l'ordine corretto.  
  
> [!NOTE]
> L'evento <xref:System.Windows.Forms.DataGridView.SortCompare> non si verifica quando viene impostata la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A> o quando il valore della proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> è `true`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Ordinamento di dati nel controllo DataGridView di Windows Form](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
