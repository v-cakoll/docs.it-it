---
title: "Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a98e57d325fc7fd9413babb45d235cbb353a0c86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form
<xref:System.Windows.Forms.DataGridView>colonne di sono disponibili tre modalità di ordinamento. La modalità di ordinamento per ogni colonna viene specificata tramite il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà della colonna, che può essere impostata su uno dei seguenti <xref:System.Windows.Forms.DataGridViewColumnSortMode> valori di enumerazione.  
  
|Valore di `DataGridViewColumnSortMode`|Descrizione|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Valore predefinito per le colonne di caselle di testo. A meno che le intestazioni di colonna vengono utilizzate per la selezione, fare clic sull'intestazione di colonna automaticamente per ordinare il <xref:System.Windows.Forms.DataGridView> da questa colonna e viene visualizzata un'icona che indica l'ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Valore predefinito per le colonne di caselle di testo non. È possibile ordinare questa colonna a livello di codice. Tuttavia, non è progettato per l'ordinamento, pertanto verrà riservato alcuno spazio per l'icona di ordinamento.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|È possibile ordinare questa colonna a livello di codice, e uno spazio riservato per l'icona di ordinamento.|  
  
 Si potrebbe voler modificare la modalità di ordinamento per una colonna che per impostazione predefinita <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> se contiene valori che possono essere ordinati. Ad esempio, se si dispone di una colonna del database contenente i numeri che rappresentano gli stati degli elementi, è possibile visualizzare questi numeri sotto forma di icone da una colonna di immagini di associazione alla colonna del database. È quindi possibile modificare i valori numerici delle celle immagini corrispondenti in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. In questo caso, l'impostazione di <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> consentirà agli utenti di ordinare la colonna. L'ordinamento automatico consentirà agli utenti di raggruppare gli elementi che presentano lo stesso stato, anche se gli stati corrispondenti ai numeri non dispone di una sequenza naturale. Le colonne di casella di controllo sono un altro esempio in cui l'ordinamento automatico è utile per il raggruppamento di elementi nello stesso stato.  
  
 È possibile ordinare un <xref:System.Windows.Forms.DataGridView> a livello di codice per i valori in qualsiasi colonna o in più colonne, indipendentemente dal <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> impostazioni. Ordinamento a livello di codice è utile quando si desidera fornire la propria interfaccia utente (UI) per l'ordinamento o quando si desidera implementare un ordinamento personalizzato. Fornisce la propria interfaccia utente di ordinamento è utile, ad esempio, quando si imposta la <xref:System.Windows.Forms.DataGridView> modalità di selezione per consentire la selezione di intestazione di colonna. In questo caso, anche se le intestazioni di colonna non possono essere utilizzate per l'ordinamento, è consigliabile comunque le intestazioni per visualizzare l'icona di ordinamento appropriata, pertanto è necessario impostare il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Colonne impostate sulla modalità di ordinamento a livello di codice non viene visualizzata automaticamente un'icona di ordinamento. Per queste colonne, è necessario visualizzare l'icona manualmente impostando il <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> proprietà. Ciò è necessario se si desidera flessibilità un ordinamento personalizzato. Ad esempio, se si ordina il <xref:System.Windows.Forms.DataGridView> da più colonne, si potrebbe voler non visualizzare icone di ordinamento più o.  
  
 Sebbene sia possibile ordinare a livello di codice un <xref:System.Windows.Forms.DataGridView> da qualsiasi colonna, alcune colonne, ad esempio le colonne di pulsanti, potrebbero non contenere valori che possono essere ordinati. Per queste colonne, una <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> impostazione della proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica che non verranno mai utilizzate per l'ordinamento, pertanto non è necessario riservare spazio dell'intestazione per l'icona di ordinamento.  
  
 Quando un <xref:System.Windows.Forms.DataGridView> è ordinato, è possibile determinare sia la colonna di ordinamento e l'ordinamento selezionando i valori del <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A> proprietà. Questi valori non sono significativi dopo un'operazione di ordinamento personalizzata. Per ulteriori informazioni sull'ordinamento personalizzato, vedere la sezione ordinamento personalizzato più avanti in questo argomento.  
  
 Quando un <xref:System.Windows.Forms.DataGridView> controllo contenente le colonne associate e non è ordinato, i valori nelle colonne non associate non vengono mantenuti automaticamente. Per mantenere tali valori, è necessario implementare la modalità virtuale impostando il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true` e la gestione di <xref:System.Windows.Forms.DataGridView.CellValueNeeded> e <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventi. Per ulteriori informazioni, vedere [procedura: implementare la modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). Ordinamento in base a colonne non associate in modalità di associazione non è supportata.  
  
## <a name="programmatic-sorting"></a>Ordinamento a livello di codice  
 È possibile ordinare un <xref:System.Windows.Forms.DataGridView> a livello di codice chiamando il relativo <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo.  
  
 Il `Sort(DataGridViewColumn,ListSortDirection)` overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo accetta un <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.ComponentModel.ListSortDirection> il valore di enumerazione come parametri. Questo overload è utile quando si ordinano le colonne con valori che possono essere ordinati, ma che non si desidera configurare per l'ordinamento automatico. Quando si chiama questo overload e di passare in una colonna con un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valore della proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A> vengono impostate automaticamente e viene visualizzata l'icona di ordinamento appropriato nell'intestazione di colonna.  
  
> [!NOTE]
>  Quando il <xref:System.Windows.Forms.DataGridView> controllo è associato a un'origine dati esterna impostando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà, il `Sort(DataGridViewColumn,ListSortDirection)` overload del metodo non funziona per le colonne non associate. Inoltre, quando il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true`, è possibile chiamare questo overload solo per le colonne associate. Per determinare se una colonna è associato a dati, controllare il <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> valore della proprietà. L'ordinamento delle colonne non associate in modalità di associazione non è supportato.  
  
## <a name="custom-sorting"></a>Ordinamento personalizzato  
 È possibile personalizzare <xref:System.Windows.Forms.DataGridView> utilizzando il `Sort(IComparer)` overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo o gestendo il <xref:System.Windows.Forms.DataGridView.SortCompare> evento.  
  
 Il `Sort(IComparer)` overload del metodo accetta un'istanza di una classe che implementa il <xref:System.Collections.IComparer> interfaccia come parametro. Questo overload è utile quando si desidera fornire l'ordinamento personalizzato. ad esempio, quando i valori in una colonna non sono un ordinamento naturale o quando l'ordine naturale è appropriata. In questo caso, non è possibile utilizzare l'ordinamento automatico, ma è comunque possibile agli utenti di ordinare facendo clic sulle intestazioni di colonna. È possibile chiamare questo overload in un gestore per il <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> evento se non si utilizzano le intestazioni di colonna per la selezione.  
  
> [!NOTE]
>  Il `Sort(IComparer)` overload del metodo funziona solo quando il <xref:System.Windows.Forms.DataGridView> non è associato a un'origine dati esterna e <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> valore della proprietà è `false`. Per personalizzare l'ordinamento delle colonne associate a un'origine dati esterna, è necessario utilizzare le operazioni di ordinamento fornite dall'origine dati. In modalità virtuale, è necessario fornire le proprie operazioni di ordinamento delle colonne non associate.  
  
 Utilizzare il `Sort(IComparer)` overload del metodo, è necessario creare una classe che implementa il <xref:System.Collections.IComparer> interfaccia. Questa interfaccia richiede la classe deve implementare il <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> metodo, al quale il <xref:System.Windows.Forms.DataGridView> passa <xref:System.Windows.Forms.DataGridViewRow> oggetti come input quando il `Sort(IComparer)` viene chiamato l'overload del metodo. Con questa operazione, è possibile calcolare l'ordinamento corretto delle righe in base ai valori in qualsiasi colonna.  
  
 Il `Sort(IComparer)` overload del metodo non viene impostato il <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> e <xref:System.Windows.Forms.DataGridView.SortOrder%2A> proprietà, è necessario impostare sempre la <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> proprietà per visualizzare l'icona di ordinamento.  
  
 In alternativa il `Sort(IComparer)` overload del metodo, è possibile specificare un ordinamento personalizzato mediante l'implementazione di un gestore per il <xref:System.Windows.Forms.DataGridView.SortCompare> evento. Questo evento si verifica quando l'utente sceglie le intestazioni delle colonne configurate per l'ordinamento automatico o quando si chiama il `Sort(DataGridViewColumn,ListSortDirection)` overload di <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo. L'evento si verifica per ogni coppia di righe nel controllo, che consente di calcolare l'ordine corretto.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.DataGridView.SortCompare> evento non viene generato quando il <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà è impostata o quando il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> valore della proprietà è `true`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>  
 [Ordinamento di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 [Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
