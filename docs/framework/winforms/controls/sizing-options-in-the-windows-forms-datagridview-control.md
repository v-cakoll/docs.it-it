---
title: Opzioni di ridimensionamento nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: 6e3a7786970ef536da4ef7628cd33ae067ba90be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opzioni di ridimensionamento nel controllo DataGridView Windows Form
<xref:System.Windows.Forms.DataGridView> le righe, colonne e intestazioni possono modificare le dimensioni in seguito a diverse occorrenze. La tabella seguente illustra tali occorrenze.  
  
|Occorrenza|Descrizione|  
|----------------|-----------------|  
|Ridimensionamento di utente|Gli utenti possono effettuare ridimensionamenti trascinando o facendo doppio clic sui separatori di riga o colonna intestazione.|  
|Ridimensionamento dei controlli|Nella modalità di riempimento di colonna, la larghezza delle colonne di modificare la larghezza del controllo cambia; ad esempio, quando il controllo viene ancorato al form padre e l'utente ridimensiona il form.|  
|Modifica del valore della cella|In modalità di ridimensionamento automatico basato sul contenuto, le dimensioni variano in funzione dei nuovi valori visualizzati.|  
|Chiamata al metodo|Ridimensionamento di basata sul contenuto a livello di codice consente di rendere ridimensionamenti opportunistici in base ai valori di cella al momento della chiamata al metodo.|  
|Impostazione della proprietà|È inoltre possibile impostare i valori di larghezza e altezza.|  
  
 Per impostazione predefinita, il ridimensionamento dell'utente è abilitato, il ridimensionamento automatico è disabilitato e i valori delle celle con dimensioni maggiori rispetto alle colonne vengono tagliati.  
  
 Nella tabella seguente vengono illustrati scenari che è possibile utilizzare per regolare il comportamento predefinito o da utilizzare specifiche opzioni di ridimensionamento per ottenere effetti particolari.  
  
|Scenario|Implementazione|  
|--------------|--------------------|  
|Usa modalità di riempimento di colonna per la visualizzazione dati in un numero relativamente ridotto di colonne che occupano l'intera larghezza del controllo senza visualizzare la barra di scorrimento orizzontale di dimensioni simili.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Utilizzare con la modalità riempimento colonna Visualizza valori di dimensioni variabili.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inizializzare la larghezza delle colonne relativo impostando la colonna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> proprietà o chiamando il controllo <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> metodo dopo aver compilato il controllo con i dati.|  
|Utilizzare la modalità di riempimento colonna con valori di importanza diversa.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Impostare grande <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> valori per le colonne che devono sempre visualizzare alcuni dei dati o utilizzare un'opzione di ridimensionamento diversa da riempire modalità per colonne specifiche.|  
|Utilizzare la modalità di riempimento colonna per evitare la visualizzazione lo sfondo del controllo.|Impostare il <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà della colonna ultimo <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> e utilizzare altre opzioni di ridimensionamento per le altre colonne. Se le altre colonne utilizzano una quantità eccessiva di spazio disponibile, impostare il <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> proprietà dell'ultima colonna.|  
|Visualizzare una colonna a larghezza fissa, ad esempio un'icona o una colonna ID.|Impostare <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> e <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.False> per la colonna. Inizializzare la larghezza impostando il <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> proprietà o chiamando il controllo <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> metodo dopo aver compilato il controllo con i dati.|  
|Regolare le dimensioni automaticamente ogni volta che il contenuto delle celle modifica per evitare il ritaglio e per ottimizzare l'utilizzo dello spazio.|Impostare una proprietà di ridimensionamento automatico su un valore che rappresenta una modalità di ridimensionamento basato sul contenuto. Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, utilizzare una modalità di ridimensionamento che calcola solo le righe visualizzate.|  
|Adattare le dimensioni i valori nelle righe visualizzate per evitare effetti negativi sulle prestazioni quando si lavora con molte righe.|Utilizzare i valori di enumerazione della modalità di ridimensionamento appropriata con il ridimensionamento automatico o a livello di codice. Per regolare le dimensioni i valori nelle righe appena visualizzate durante lo scorrimento, chiamare un metodo di ridimensionamento in un <xref:System.Windows.Forms.DataGridView.Scroll> gestore dell'evento. Fare doppio clic su utente di personalizzare il ridimensionamento in modo che solo i valori nelle righe visualizzate determinano le nuove dimensioni, chiamare un metodo di ridimensionamento in un <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> o <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> gestore dell'evento.|  
|Adattare le dimensioni contenuto delle celle solo in orari specifici per evitare effetti negativi sulle prestazioni o per consentire il ridimensionamento dell'utente.|Chiamare un metodo di ridimensionamento basato sul contenuto in un gestore eventi. Ad esempio, utilizzare il <xref:System.Windows.Forms.DataGridView.DataBindingComplete> eventi per inizializzare le dimensioni dopo l'associazione e gestire il <xref:System.Windows.Forms.DataGridView.CellValidated> o <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento per regolare le dimensioni per compensare le modifiche o modifiche dell'utente in un'origine dati associata.|  
|Modificare l'altezza delle righe per il contenuto delle celle su più righe.|Verificare che la larghezza delle colonne siano appropriate per la visualizzazione dei paragrafi di testo e utilizzare ridimensionamento di righe basato sul contenuto automatico o a livello di codice per regolare l'altezza. Verificare inoltre che le celle con contenuto su più righe vengono visualizzate utilizzando un <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> il valore di stile di cella <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> In genere, si utilizzerà una modalità di ridimensionamento automatico delle colonne per mantenere la larghezza delle colonne o set su una larghezza specifica prima regolata.|  
  
## <a name="resizing-with-the-mouse"></a>Ridimensionamento con il Mouse  
 Per impostazione predefinita, gli utenti possono ridimensionare le righe, colonne e le intestazioni che non utilizzano una modalità di ridimensionamento automatico in base ai valori di cella. Per impedire agli utenti di ridimensionamento con altre modalità, ad esempio la modalità di riempimento di colonna, impostare una o più dei seguenti <xref:System.Windows.Forms.DataGridView> proprietà:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 È inoltre possibile impedire agli utenti di ridimensionare le singole righe o colonne impostando i relativi <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> proprietà. Per impostazione predefinita, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà è basato sul <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> valore della proprietà per le colonne e <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> valore della proprietà per le righe. Se si imposta in modo esplicito <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.True> o <xref:System.Windows.Forms.DataGridViewTriState.False>, tuttavia, gli override del valore specificato è il valore di controllo per tale riga o colonna. Impostare <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.NotSet> per ripristinare l'ereditarietà.  
  
 Poiché <xref:System.Windows.Forms.DataGridViewTriState.NotSet> Ripristina l'ereditarietà del valore, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> proprietà non restituisce mai un <xref:System.Windows.Forms.DataGridViewTriState.NotSet> valore a meno che la riga o colonna non è stato aggiunto a un <xref:System.Windows.Forms.DataGridView> controllo. Se è necessario determinare se il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà di una riga o colonna viene ereditato, esaminare il relativo <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà. Se il <xref:System.Windows.Forms.DataGridViewElement.State%2A> valore include il <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> flag, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà non viene ereditato.  
  
## <a name="automatic-sizing"></a>Ridimensionamento automatico  
 Esistono due tipi di ridimensionamento automatico nel <xref:System.Windows.Forms.DataGridView> controllo: modalità di riempimento di colonna e il ridimensionamento automatico basato sul contenuto.  
  
 Modalità di riempimento di colonna, le colonne visibili nel controllo per riempire la larghezza dell'area di visualizzazione del controllo. Per ulteriori informazioni su questa modalità, vedere [modalità di riempimento delle colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 È anche possibile configurare le righe, colonne e intestazioni di regolare automaticamente le dimensioni per adattarsi al contenuto della cella. In questo caso, il ridimensionamento viene eseguito ogni volta che cambia il contenuto delle celle.  
  
> [!NOTE]
>  Se si gestiscono i valori di cella in una cache di dati personalizzati utilizzando la modalità virtuale, il ridimensionamento automatico si verifica quando l'utente modifica il valore di una cella ma non si verifica quando si modifica un valore memorizzato nella cache di fuori di un <xref:System.Windows.Forms.DataGridView.CellValuePushed> gestore dell'evento. In questo caso, chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo per forzare il controllo per aggiornare la visualizzazione della cella e applicare la modalità di ridimensionamento automatico corrente.  
  
 Se il ridimensionamento automatico basato sul contenuto è abilitato per una sola dimensione, che, per righe, ma non colonne o per le colonne ma non le righe, e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitata, si verifica anche ogni volta che l'altra dimensione. Se, ad esempio, righe e colonne non sono configurate per il ridimensionamento automatico e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitata, gli utenti possono trascinare i separatori di colonna per modificare la larghezza di una colonna e l'altezza delle righe verrà regolato automaticamente in modo che il contenuto delle celle è ancora completamente visualizzato.  
  
 Se si configura sia righe e colonne per il ridimensionamento automatico basato sul contenuto e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitato, il <xref:System.Windows.Forms.DataGridView> controllo adatterà le dimensioni, ogni volta che il contenuto delle celle cambia e utilizzerà un rapporto di altezza e la larghezza delle celle ideale nel calcolo delle dimensioni di nuovo.  
  
 Per configurare la modalità di ridimensionamento per le intestazioni e le righe e per le colonne che non superano il valore del controllo, impostare uno o più dei seguenti <xref:System.Windows.Forms.DataGridView> proprietà:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Per eseguire l'override di modalità di ridimensionamento di colonne del controllo per una singola colonna, impostare il relativo <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà su un valore diverso da <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. La modalità di ridimensionamento per una colonna è determinata dal relativo <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> proprietà. Il valore di questa proprietà è in base alla colonna <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> valore della proprietà, a meno che tale valore sia <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, nel qual caso il controllo <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> valore ereditato.  
  
 Utilizzare in base al contenuto il ridimensionamento automatico con cautela quando si lavora con grandi quantità di dati. Per evitare effetti negativi sulle prestazioni, utilizzare la modalità di ridimensionamento automatico che consentono di calcolare le dimensioni basato solo su righe visualizzate anziché un'analisi di ogni riga nel controllo. Per ottenere prestazioni ottimali, utilizzare a livello di codice invece il ridimensionamento in modo da poter ridimensionare in momenti specifici, ad esempio immediatamente dopo i nuovi dati verrà caricato.  
  
 Modalità di ridimensionamento automatico basato sul contenuto non influiscono le righe, colonne o intestazioni nascoste impostando la riga o colonna <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> proprietà o il controllo <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> o <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> proprietà `false`. Ad esempio, se una colonna viene nascosto dopo che viene ridimensionata automaticamente per contenere un valore di cella di grandi dimensioni, la colonna nascosta non modificherà la dimensione se viene eliminata la riga contenente il valore della cella di grandi dimensioni. Ridimensionamento automatico non si verifica quando cambia la visibilità, pertanto la modifica della colonna <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> proprietà nuovamente a `true` non forza il ricalcolo delle dimensioni in base al contenuto corrente.  
  
 Ridimensionamento di basata sul contenuto a livello di codice influisce sulle righe, colonne e intestazioni indipendentemente dalla visibilità.  
  
## <a name="programmatic-resizing"></a>Il ridimensionamento a livello di codice  
 Quando il ridimensionamento automatico è disabilitato, è possibile impostare a livello di codice la larghezza esatta o l'altezza delle righe, colonne o intestazioni attraverso le proprietà seguenti:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 Anche a livello di codice, è possibile ridimensionare righe, colonne e intestazioni in base al contenuto nei modi seguenti:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Questi metodi verranno ridimensionare righe, colonne, o intestazioni una sola volta anziché configurarli per il ridimensionamento continuo. Le nuove dimensioni vengono calcolate automaticamente per visualizzare tutto il contenuto senza troncamenti. Quando si ridimensionano a livello di programmazione le colonne contenenti <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> i valori della proprietà <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, tuttavia, la larghezza calcolata in base al contenuto consentono di modificare in modo proporzionale la colonna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> i valori delle proprietà e la colonna effettivamente larghezze sono quindi viene calcolata in base a queste nuove proporzioni affinché tutte le colonne riempire l'area di visualizzazione disponibile del controllo.  
  
 Il ridimensionamento a livello di codice è utile per evitare effetti negativi sulle prestazioni con il ridimensionamento continuo. È inoltre utile fornire le dimensioni iniziali per le intestazioni, colonne e righe ridimensionabili dall'utente e per la modalità di riempimento di colonna.  
  
 In genere si chiamerà i metodi di ridimensionamento a livello di codice in momenti specifici. Ad esempio, si potrebbero ridimensionare a livello di programmazione tutte le colonne immediatamente dopo il caricamento dei dati oppure si può ridimensionare a livello di codice una riga specifica dopo che è stato modificato un valore di cella determinato.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizzazione del comportamento di ridimensionamento in base al contenuto  
 È possibile personalizzare i comportamenti di ridimensionamento quando si lavora con derivata <xref:System.Windows.Forms.DataGridView> tipi di cella, riga e colonna eseguendo l'override di <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, o <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> metodi o chiamando protetto ridimensionamento overload del metodo in una classe <xref:System.Windows.Forms.DataGridView> controllo. Gli overload del metodo di ridimensionamento protetti sono progettate per funzionare in coppie per ottenere un rapporto di altezza e la larghezza delle celle ideale, evitando celle eccessivamente larghezza e un'altezza. Ad esempio, se si chiama il `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` overload di <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> metodo e passa un valore di `false` per il <xref:System.Boolean> parametro, l'overload calcolerà l'altezza e larghezza ideali per le celle nella riga, ma verrà regolare l'altezza delle righe solo. È quindi necessario chiamare il <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> metodo per regolare la larghezza delle colonne al valore calcolato ideale.  
  
## <a name="content-based-sizing-options"></a>Opzioni di ridimensionamento basato sul contenuto  
 Le enumerazioni utilizzate dai metodi e proprietà di ridimensionamento avere valori simili per il ridimensionamento basato sul contenuto. Con questi valori, è possibile limitare le celle vengono utilizzate per calcolare le dimensioni preferite. Per tutte le enumerazioni di ridimensionamento, i valori con nomi che fanno riferimento alle celle visualizzate limitano il calcolo alle celle nelle righe visualizzate. Esclusione di righe è utile per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di righe. È inoltre possibile limitare i calcoli in valori di cella nelle celle di intestazione o di altro tipo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Modalità di riempimento di colonna nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare le modalità dimensionamento del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
