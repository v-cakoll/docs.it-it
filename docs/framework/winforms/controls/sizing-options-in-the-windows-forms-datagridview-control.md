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
ms.openlocfilehash: a236289939b9355e961ce1bfc9a7e0ff5349a95a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717908"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opzioni di ridimensionamento nel controllo DataGridView Windows Form
<xref:System.Windows.Forms.DataGridView> le intestazioni, colonne e righe è possono modificare le dimensioni in seguito a diverse occorrenze. La tabella seguente illustra queste occorrenze.  
  
|occorrenza|Descrizione|  
|----------------|-----------------|  
|Ridimensionamento di utente|Gli utenti possono apportare modifiche di dimensione trascinando o facendo doppio clic sui separatori di riga, colonna o nell'intestazione.|  
|Ridimensionamento dei controlli|In modalità riempimento delle colonne, modifica la larghezza delle colonne quando viene modificata la larghezza del controllo; ad esempio, quando è ancorato il controllo al form padre e l'utente ridimensiona il form.|  
|Modifica del valore di cella|Nelle modalità di ridimensionamento automatico basato su contenuto, le dimensioni variano in funzione dei nuovi valori visualizzati.|  
|Chiamata al metodo|Ridimensionamento a livello di codice basato sul contenuto consente di apportare modifiche di dimensione opportunistici basati sui valori di cella al momento della chiamata al metodo.|  
|Impostazione della proprietà|È anche possibile impostare valori di larghezza e altezza specifica.|  
  
 Per impostazione predefinita, il ridimensionamento dell'utente è abilitato, il ridimensionamento automatico è disabilitato e i valori delle celle con dimensioni maggiori rispetto alle relative colonne vengono tagliati.  
  
 Nella tabella seguente vengono illustrati scenari che è possibile usare per regolare il comportamento predefinito o usare le opzioni di ridimensionamento specifico per ottenere effetti particolari.  
  
|Scenario|Implementazione|  
|--------------|--------------------|  
|Modalità di riempimento delle colonne usare per la visualizzazione dei dati in un numero relativamente ridotto di colonne che occupano l'intera larghezza del controllo senza visualizzare la barra di scorrimento orizzontale di dimensioni simili.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Usa modalità di riempimento di colonna con Visualizza valori di dimensioni variabili.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inizializzare la larghezza delle colonne relativo impostando la colonna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> delle proprietà o chiamando il controllo <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> metodo dopo aver compilato il controllo con i dati.|  
|Usare modalità riempimento delle colonne con valori di priorità diversi.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Impostare grande <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> i valori per le colonne che devono sempre visualizzare alcuni dei propri dati o usare un'opzione di ridimensionamento diverso da riempire la modalità per colonne specifiche.|  
|Usare modalità riempimento delle colonne per evitare di visualizzare lo sfondo del controllo.|Impostare il <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà dell'ultima colonna a <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> e usare altre opzioni di ridimensionamento per le altre colonne. Se le altre colonne utilizzano una quantità eccessiva di spazio disponibile, impostare il <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> proprietà dell'ultima colonna.|  
|Visualizzare una colonna a larghezza fissa, ad esempio un'icona o una colonna ID.|Impostare <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> al <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> e <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.False> per la colonna. Inizializzare la larghezza impostando il <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> proprietà oppure chiamando il controllo <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> metodo dopo aver compilato il controllo con i dati.|  
|Regolare le dimensioni automaticamente ogni volta che il contenuto delle celle modificata per evitare il ritaglio e per ottimizzare l'utilizzo dello spazio.|Impostare una proprietà di ridimensionamento automatico su un valore che rappresenta una modalità di ridimensionamento basata sul contenuto. Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, utilizzare una modalità di ridimensionamento che calcola solo le righe visualizzate.|  
|Regolare le dimensioni i valori nelle righe visualizzate per evitare effetti negativi sulle prestazioni quando si lavora con molte righe.|Usare i valori di enumerazione appropriati in modalità di ridimensionamento con il ridimensionamento automatico o a livello di codice. Per regolare le dimensioni ai valori nelle righe appena visualizzate durante lo scorrimento, chiamare un metodo di ridimensionamento in un <xref:System.Windows.Forms.DataGridView.Scroll> gestore dell'evento. Fare doppio clic su utente di personalizzare il ridimensionamento in modo che solo i valori nelle righe visualizzate determinano le nuove dimensioni, chiamare un metodo di ridimensionamento in un <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> o <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> gestore dell'evento.|  
|Adattare le dimensioni contenuto delle celle solo in orari specifici per evitare effetti negativi sulle prestazioni o per abilitare il ridimensionamento dell'utente.|Chiamare un metodo di ridimensionamento basata sul contenuto in un gestore eventi. Ad esempio, usare il <xref:System.Windows.Forms.DataGridView.DataBindingComplete> eventi per inizializzare le dimensioni dopo l'associazione e gestire il <xref:System.Windows.Forms.DataGridView.CellValidated> o <xref:System.Windows.Forms.DataGridView.CellValueChanged> evento per regolare le dimensioni per compensare la modifica dell'utente o le modifiche in un'origine dati associata.|  
|Regolare l'altezza delle righe per il contenuto delle celle su più righe.|Assicurarsi che la larghezza delle colonne siano appropriati per la visualizzazione dei paragrafi di testo e utilizzare il ridimensionamento automatico o a livello di programmazione riga basato sul contenuto per regolare l'altezza. Verificare inoltre che le celle con contenuto a più righe vengono visualizzate utilizzando un <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> valore di stile di cella <xref:System.Windows.Forms.DataGridViewTriState.True>.<br /><br /> In genere, si userà una modalità di ridimensionamento automatico delle colonne per mantenere la larghezza delle colonne o per impostarli su una larghezza specifica prima viene regolata.|  
  
## <a name="resizing-with-the-mouse"></a>Il ridimensionamento con il Mouse  
 Per impostazione predefinita, gli utenti possono ridimensionare le righe, colonne e le intestazioni che non usano una modalità di ridimensionamento automatico basata sui valori di cella. Per impedire agli utenti di ridimensionare con altre modalità, ad esempio la modalità di riempimento di colonna, impostare uno o più dei seguenti <xref:System.Windows.Forms.DataGridView> proprietà:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 È anche possibile impedire agli utenti di ridimensionare le singole righe o colonne impostando i <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> proprietà. Per impostazione predefinita, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà è basato sul <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> valore della proprietà per le colonne e <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> valore della proprietà per le righe. Se si imposta in modo esplicito <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> al <xref:System.Windows.Forms.DataGridViewTriState.True> o <xref:System.Windows.Forms.DataGridViewTriState.False>, tuttavia, le sostituzioni di valore specificato è il valore di controllo per tale riga o colonna. Impostare <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> a <xref:System.Windows.Forms.DataGridViewTriState.NotSet> per ripristinare l'ereditarietà.  
  
 Poiché <xref:System.Windows.Forms.DataGridViewTriState.NotSet> Ripristina l'ereditarietà del valore, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> proprietà non restituirà mai un <xref:System.Windows.Forms.DataGridViewTriState.NotSet> valore a meno che la riga o colonna non è stato aggiunto a un <xref:System.Windows.Forms.DataGridView> controllo. Se è necessario determinare se il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà di una riga o colonna viene ereditata, esaminare il <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà. Se il <xref:System.Windows.Forms.DataGridViewElement.State%2A> valore include le <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> flag, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà non è ereditato.  
  
## <a name="automatic-sizing"></a>Ridimensionamento automatico  
 Esistono due tipi di ridimensionamento automatico nel <xref:System.Windows.Forms.DataGridView> controllo: modalità riempimento delle colonne e il ridimensionamento automatico basato sul contenuto.  
  
 Modalità riempimento delle colonne, le colonne visibili nel controllo per riempire la larghezza dell'area di visualizzazione del controllo. Per altre informazioni su questa modalità, vedere [modalità di riempimento delle colonne nel controllo DataGridView Windows Form](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 È anche possibile configurare le righe, colonne e le intestazioni per regolare automaticamente le relative dimensioni per adattarsi al contenuto della cella. In questo caso, il ridimensionamento viene eseguito ogni volta che cambia il contenuto delle celle.  
  
> [!NOTE]
>  Se si mantengono i valori delle celle in una cache di dati personalizzati usando la modalità virtuale, il ridimensionamento automatico si verifica quando l'utente modifica il valore di una cella ma non si verifica quando si modifica un valore memorizzato nella cache all'esterno di un <xref:System.Windows.Forms.DataGridView.CellValuePushed> gestore dell'evento. In questo caso, chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo per forzare il controllo per aggiornare la visualizzazione della cella e applicare la modalità di ridimensionamento automatico corrente.  
  
 Se è abilitato il ridimensionamento automatico basato sul contenuto per una sola dimensione, che è, per righe, ma non le colonne o per colonne, ma non le righe, ovvero e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> viene inoltre abilitata, si verifica anche ogni volta che l'altra dimensione. Se, ad esempio, righe e colonne non sono configurate per il ridimensionamento automatico e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitata, gli utenti possono trascinare i separatori di colonna per modificare la larghezza di una colonna e altezze regolerà automaticamente in modo che il contenuto delle celle è ancora completamente visualizzato.  
  
 Se si configura sia righe e colonne per il ridimensionamento automatico basato sul contenuto e <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitata, il <xref:System.Windows.Forms.DataGridView> controllo regolerà dimensioni ogni volta che il contenuto delle celle modificate e utilizzerà un rapporto di altezza e larghezza di cella ideale quando si calcola nuove dimensioni.  
  
 Per configurare la modalità di ridimensionamento per le intestazioni e le righe e per le colonne che non superano il valore del controllo, impostare uno o più dei seguenti <xref:System.Windows.Forms.DataGridView> proprietà:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Per eseguire l'override di modalità di ridimensionamento di colonne del controllo per una singola colonna, impostare relativi <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà su un valore diverso da <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>. La modalità di ridimensionamento per una colonna è determinata dal relativo <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> proprietà. Il valore di questa proprietà è basato della colonna <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> valore della proprietà, a meno che tale valore è <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, nel qual caso il controllo <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> valore viene ereditato.  
  
 Usare il contenuto in base al ridimensionamento automatico con cautela quando si lavora con grandi quantità di dati. Per evitare effetti negativi sulle prestazioni, utilizzare la modalità di ridimensionamento automatico che consentono di calcolare le dimensioni basate solo sulle righe visualizzate anziché un'analisi di ogni riga nel controllo. Per ottenere prestazioni ottimali, usare a livello di codice invece per il ridimensionamento in modo da poter ridimensionare a orari specifici, ad esempio immediatamente dopo i nuovi dati verrà caricato.  
  
 Modalità di ridimensionamento automatico basato su contenuto non influiscono le righe, colonne o le intestazioni che sono stati nascosti impostando la riga o colonna <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> proprietà o il controllo <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> oppure <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> delle proprietà per `false`. Ad esempio, se una colonna viene nascosto dopo che viene ridimensionata automaticamente per rientrare un valore di cella di grandi dimensioni, la colonna nascosta non passerà dimensioni se viene eliminata la riga che contiene il valore della cella di grandi dimensioni. Il ridimensionamento automatico non si verifica quando viene modificata la visibilità, pertanto la modifica della colonna <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> proprietà verso `true` non viene forzato il ricalcolo delle dimensioni in base al contenuto corrente.  
  
 Ridimensionamento di basata sul contenuto a livello di codice influisce sulle righe, colonne e intestazioni indipendentemente dalla rispettiva visibilità.  
  
## <a name="programmatic-resizing"></a>Il ridimensionamento a livello di codice  
 Quando il ridimensionamento automatico è disabilitato, è possibile impostare a livello di codice la larghezza esatta o l'altezza delle righe, colonne o delle intestazioni tramite le proprietà seguenti:  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 È possibile ridimensionare anche a livello di programmazione le righe, colonne e le intestazioni per adattarla al relativo contenuto usando i metodi seguenti:  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Questi metodi verranno ridimensionate le righe, colonne, o le intestazioni una sola volta anziché sulla relativa configurazione per il ridimensionamento continuo. Le nuove dimensioni vengono calcolate automaticamente per visualizzare tutto il contenuto senza troncamenti. Quando si ridimensionano a livello di programmazione le colonne contenenti <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> i valori della proprietà <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>, tuttavia, la larghezza calcolata basato sul contenuto viene usata per modificare in modo proporzionale alla colonna <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> i valori delle proprietà e la colonna effettivamente larghezze sono quindi calcolato in base a queste nuove proporzioni in modo che tutte le colonne è riempire l'area di visualizzazione disponibili del controllo.  
  
 Il ridimensionamento a livello di codice è utile per evitare la riduzione delle prestazioni con ridimensionamento continua. È anche utile fornire le dimensioni iniziali per le intestazioni, colonne e righe ridimensionabili dall'utente e per la modalità di riempimento di colonna.  
  
 In genere si chiamerà i metodi di ridimensionamento a livello di codice in momenti specifici. Ad esempio, si potrebbero ridimensionare tutte le colonne a livello di codice immediatamente dopo il caricamento dei dati, oppure è a livello di codice potrebbe ridimensionare una riga specifica dopo che un valore di cella specifica è stato modificato.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizzazione del comportamento di ridimensionamento basata sul contenuto  
 È possibile personalizzare i comportamenti di ridimensionamento quando si lavora con derivato <xref:System.Windows.Forms.DataGridView> tipi di cella, riga e colonna eseguendo l'override di <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, o <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> metodi o tramite la chiamata protetta overload di metodo di ridimensionamento in un oggetto derivato <xref:System.Windows.Forms.DataGridView> controllo. Overload del metodo di ridimensionamento protetto sono progettati per funzionare in coppie per ottenere un rapporto di altezza e larghezza delle celle ideale, evitando le celle eccessivamente vasta e un'altezza. Ad esempio, se si chiama il `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` eseguire l'overload del <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> metodo e passare un valore di `false` per il <xref:System.Boolean> parametro, l'overload di calcolare l'altezza e larghezza ideali per le celle nella riga, ma si adatterà all'altezza delle righe solo. È quindi necessario chiamare il <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> metodo per regolare la larghezza delle colonne per la soluzione ideale calcolata.  
  
## <a name="content-based-sizing-options"></a>Opzioni di ridimensionamento basata sul contenuto  
 Le enumerazioni utilizzate da metodi e proprietà di ridimensionamento hanno valori simili per il dimensionamento basato sul contenuto. Con questi valori, è possibile limitare le celle vengono utilizzate per calcolare le dimensioni preferite. Per tutte le enumerazioni di ridimensionamento, i valori con nomi che fanno riferimento alle celle visualizzate limitano il calcolo alle celle nelle righe visualizzate. Esclusione di righe è utile per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di righe. È inoltre possibile limitare i calcoli sui valori di cella nelle celle di intestazione o di altro tipo.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Modalità di riempimento di colonna nel controllo DataGridView di Windows Form](column-fill-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare le modalità dimensionamento del controllo DataGridView Windows Form](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
