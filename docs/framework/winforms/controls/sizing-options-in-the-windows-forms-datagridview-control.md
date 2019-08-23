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
ms.openlocfilehash: a8e2e05877746dfb043b7e8ac2a6c2b7017883c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960429"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Opzioni di ridimensionamento nel controllo DataGridView Windows Form
<xref:System.Windows.Forms.DataGridView>le dimensioni delle righe, delle colonne e delle intestazioni possono variare in seguito a diverse occorrenze. Nella tabella seguente vengono illustrate queste occorrenze.  
  
|Occorrenza|Descrizione|  
|----------------|-----------------|  
|Ridimensionamento utente|Gli utenti possono apportare modifiche alle dimensioni trascinando o facendo doppio clic su righe, colonne o divisori di intestazione.|  
|Ridimensionamento controllo|In modalità di riempimento a colonne, la larghezza delle colonne cambia quando viene modificata la larghezza del controllo; ad esempio, quando il controllo è ancorato al form padre e l'utente ridimensiona il form.|  
|Modifica valore cella|Nelle modalità di ridimensionamento automatico basate sul contenuto, le dimensioni cambiano per adattarsi ai nuovi valori di visualizzazione.|  
|Chiamata al metodo|Il ridimensionamento basato sul contenuto programmatico consente di apportare modifiche di dimensioni opportunistiche in base ai valori delle celle al momento della chiamata al metodo.|  
|Impostazione proprietà|È inoltre possibile impostare valori di altezza e larghezza specifici.|  
  
 Per impostazione predefinita, il ridimensionamento dell'utente è abilitato, il ridimensionamento automatico è disabilitato e i valori delle celle più larghi delle rispettive colonne vengono ritagliati.  
  
 La tabella seguente illustra gli scenari che è possibile usare per modificare il comportamento predefinito o per usare opzioni di ridimensionamento specifiche per ottenere effetti specifici.  
  
|Scenario|Implementazione|  
|--------------|--------------------|  
|Usare la modalità di riempimento delle colonne per visualizzare dati di dimensioni simili in un numero relativamente ridotto di colonne che occupano l'intera larghezza del controllo senza visualizzare la barra di scorrimento orizzontale.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>.|  
|Utilizzare la modalità di riempimento a colonne con valori di dimensioni variabili.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Inizializzare la larghezza delle colonne relative impostando <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> le proprietà della colonna o chiamando <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> il metodo del controllo dopo aver compilato il controllo con i dati.|  
|Usare la modalità di riempimento delle colonne con valori di importanza variabile.|Impostare la proprietà <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>. Impostare valori <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> di grandi dimensioni per le colonne che devono sempre visualizzare alcuni dati oppure utilizzare un'opzione di ridimensionamento diversa dalla modalità di riempimento per colonne specifiche.|  
|Utilizzare la modalità di riempimento delle colonne per evitare di visualizzare lo sfondo del controllo.|Impostare la <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà dell'ultima colonna su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> e utilizzare altre opzioni di ridimensionamento per le altre colonne. Se nelle altre colonne viene utilizzata una quantità eccessiva di spazio disponibile, impostare <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> la proprietà dell'ultima colonna.|  
|Visualizza una colonna a larghezza fissa, ad esempio una colonna icona o ID.|Impostare <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> su <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> e <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> su perlacolonna.<xref:System.Windows.Forms.DataGridViewTriState.False> Inizializzare la larghezza impostando <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> la proprietà o chiamando il metodo <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> del controllo dopo aver compilato il controllo con i dati.|  
|Regolare automaticamente le dimensioni ogni volta che il contenuto delle celle viene modificato per evitare il ritaglio e ottimizzare l'utilizzo dello spazio.|Impostare una proprietà di ridimensionamento automatico su un valore che rappresenta una modalità di ridimensionamento basata sul contenuto. Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, utilizzare una modalità di ridimensionamento che calcola solo le righe visualizzate.|  
|Modificare le dimensioni per adattare i valori nelle righe visualizzate per evitare le penalizzazioni delle prestazioni quando si utilizzano molte righe.|Usare i valori di enumerazione appropriati in modalità di ridimensionamento con il ridimensionamento automatico o a livello di codice. Per regolare le dimensioni in base ai valori nelle righe appena visualizzate durante lo scorrimento, chiamare un metodo di ridimensionamento in un <xref:System.Windows.Forms.DataGridView.Scroll> gestore eventi. Per personalizzare il ridimensionamento del doppio clic dell'utente in modo che solo i valori nelle righe visualizzate determinino le nuove dimensioni, chiamare <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> un <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> metodo di ridimensionamento in un gestore eventi o.|  
|Regolare le dimensioni in base al contenuto delle celle solo in momenti specifici per evitare le penalizzazioni delle prestazioni o per abilitare il ridimensionamento degli utenti.|Chiamare un metodo di ridimensionamento basato sul contenuto in un gestore eventi. Utilizzare, ad esempio, <xref:System.Windows.Forms.DataGridView.DataBindingComplete> l'evento per inizializzare le dimensioni dopo l'associazione <xref:System.Windows.Forms.DataGridView.CellValidated> e <xref:System.Windows.Forms.DataGridView.CellValueChanged> gestire l'evento o per modificare le dimensioni per compensare le modifiche o le modifiche dell'utente in un'origine dati associata.|  
|Modificare le altezze delle righe per il contenuto delle celle su più righe|Verificare che le larghezze delle colonne siano appropriate per visualizzare i paragrafi di testo e utilizzare il ridimensionamento delle righe basato sul contenuto automatico o programmatico per regolare le altezze. Assicurarsi inoltre che le celle con contenuto su più righe vengano <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> visualizzate utilizzando un valore <xref:System.Windows.Forms.DataGridViewTriState.True>di stile di cella.<br /><br /> In genere, si utilizzerà una modalità di ridimensionamento automatico delle colonne per mantenere le larghezze delle colonne o impostarle su larghezze specifiche prima di modificare le altezze delle righe.|  
  
## <a name="resizing-with-the-mouse"></a>Ridimensionamento con il mouse  
 Per impostazione predefinita, gli utenti possono ridimensionare le righe, le colonne e le intestazioni che non utilizzano una modalità di ridimensionamento automatico in base ai valori delle celle. Per impedire agli utenti di ridimensionarsi con altre modalità, ad esempio la modalità di riempimento delle colonne, impostare una o <xref:System.Windows.Forms.DataGridView> più delle proprietà seguenti:  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 È inoltre possibile impedire agli utenti di ridimensionare singole righe o colonne impostando <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> le relative proprietà. Per impostazione predefinita, <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> il valore della proprietà è basato <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> sul valore della proprietà per le <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> colonne e sul valore della proprietà per le righe. Se si imposta <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> in modo esplicito <xref:System.Windows.Forms.DataGridViewTriState.False>su <xref:System.Windows.Forms.DataGridViewTriState.True> o, tuttavia, il valore specificato sostituisce il valore del controllo per la riga o la colonna. Impostare <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> su<xref:System.Windows.Forms.DataGridViewTriState.NotSet> per ripristinare l'ereditarietà.  
  
 Poiché <xref:System.Windows.Forms.DataGridViewTriState.NotSet> consente di ripristinare l'ereditarietà del valore, <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> la proprietà non restituirà <xref:System.Windows.Forms.DataGridViewTriState.NotSet> mai un valore a meno che la riga o la colonna non sia <xref:System.Windows.Forms.DataGridView> stata aggiunta a un controllo. Se è necessario determinare se il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà di una riga o di una colonna viene ereditato, <xref:System.Windows.Forms.DataGridViewElement.State%2A> esaminarne la proprietà. Se il <xref:System.Windows.Forms.DataGridViewElement.State%2A> valore include il <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> flag, il <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> valore della proprietà non viene ereditato.  
  
## <a name="automatic-sizing"></a>Dimensionamento automatico  
 Il controllo include due tipi di ridimensionamento automatico <xref:System.Windows.Forms.DataGridView> : la modalità di riempimento delle colonne e il ridimensionamento automatico basato sul contenuto.  
  
 Con la modalità di riempimento a colonne, le colonne visibili del controllo riempiono la larghezza dell'area di visualizzazione del controllo. Per altre informazioni su questa modalità, vedere [modalità di riempimento delle colonne nel controllo DataGridView Windows Forms](column-fill-mode-in-the-windows-forms-datagridview-control.md).  
  
 È inoltre possibile configurare righe, colonne e intestazioni per regolare automaticamente le dimensioni in base al contenuto delle celle. In questo caso, la regolazione delle dimensioni viene eseguita ogni volta che il contenuto della cella cambia.  
  
> [!NOTE]
> Se si gestiscono i valori delle celle in una cache di dati personalizzata usando la modalità virtuale, il ridimensionamento automatico si verifica quando l'utente modifica un valore di cella ma non si verifica quando <xref:System.Windows.Forms.DataGridView.CellValuePushed> si modifica un valore memorizzato nella cache all'esterno di un gestore eventi. In questo caso, chiamare il <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> metodo per forzare il controllo ad aggiornare la visualizzazione della cella e applicare le modalità di ridimensionamento automatico correnti.  
  
 Se il dimensionamento automatico basato sul contenuto è abilitato solo per una dimensione, ovvero per le righe ma non per le colonne o per le colonne ma non <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> per le righe, ed è abilitato, anche la regolazione delle dimensioni viene eseguita ogni volta che viene modificata l'altra dimensione. Se, ad esempio, le righe ma non le colonne sono configurate per il ridimensionamento automatico ed <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> è abilitato, gli utenti possono trascinare i divisori di colonna per modificare la larghezza di una colonna e le altezze delle righe verranno regolate automaticamente in modo che il contenuto delle celle sia ancora completamente visualizzato.  
  
 Se si configurano le righe e le colonne per il ridimensionamento <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> automatico basato sul contenuto <xref:System.Windows.Forms.DataGridView> ed è abilitata, il controllo modificherà le dimensioni ogni volta che il contenuto delle celle viene modificato e utilizzerà un rapporto tra altezza e larghezza della cella ideale per il calcolo di nuove dimensioni.  
  
 Per configurare la modalità di ridimensionamento per intestazioni e righe e per le colonne che non eseguono l'override del valore del controllo, impostare una <xref:System.Windows.Forms.DataGridView> o più delle proprietà seguenti:  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 Per eseguire l'override della modalità di ridimensionamento delle colonne del controllo per una <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> singola colonna, impostarne la <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>proprietà su un valore diverso da. La modalità di ridimensionamento per una colonna è effettivamente determinata <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> dalla relativa proprietà. Il valore di questa proprietà è basato sul valore della <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> proprietà della colonna, a meno che tale valore non sia <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>, nel <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> qual caso il valore del controllo viene ereditato.  
  
 Usare il ridimensionamento automatico basato sul contenuto con cautela quando si lavora con grandi quantità di dati. Per evitare le penalizzazioni delle prestazioni, utilizzare le modalità di ridimensionamento automatico che calcolano le dimensioni in base alle righe visualizzate anziché analizzare ogni riga nel controllo. Per ottenere prestazioni ottimali, usare invece il ridimensionamento a livello di codice in modo che sia possibile ridimensionare in momenti specifici, ad esempio subito dopo il caricamento dei nuovi dati.  
  
 Le modalità di ridimensionamento automatico basate sul contenuto non influiscono su righe, colonne o intestazioni nascoste impostando la proprietà di riga <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> o colonna oppure il <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> controllo <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> o le `false`proprietà su. Se, ad esempio, una colonna viene nascosta dopo che è stata ridimensionata automaticamente per adattarsi a un valore di cella di grandi dimensioni, la colonna nascosta non ne modificherà la dimensione se la riga contenente il valore di cella grande viene eliminata. Il ridimensionamento automatico non si verifica quando viene modificata la visibilità, <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> quindi la modifica `true` della proprietà della colonna in non impone il ricalcolo delle dimensioni in base al contenuto corrente.  
  
 Il ridimensionamento basato sul contenuto programmatico influiscono su righe, colonne e intestazioni indipendentemente dalla loro visibilità.  
  
## <a name="programmatic-resizing"></a>Ridimensionamento a livello di codice  
 Quando il ridimensionamento automatico è disabilitato, è possibile impostare a livello di codice la larghezza o l'altezza esatta di righe, colonne o intestazioni tramite le proprietà seguenti:  
  
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 È anche possibile ridimensionare a livello di codice le righe, le colonne e le intestazioni per adattarle al relativo contenuto usando i metodi seguenti:  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 Questi metodi consentono di ridimensionare le righe, le colonne o le intestazioni una volta anziché configurarle per il ridimensionamento continuo. Le nuove dimensioni vengono calcolate automaticamente per visualizzare tutto il contenuto della cella senza ritaglio. Quando si ridimensionano a livello di codice <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> le colonne con <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>valori di proprietà di, tuttavia, le larghezze basate sul contenuto calcolate vengono utilizzate <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> per modificare in modo proporzionale i valori delle proprietà della colonna e la larghezza effettiva delle colonne è quindi calcolata in base a queste nuove proporzioni in modo che tutte le colonne riempiano l'area di visualizzazione disponibile del controllo.  
  
 Il ridimensionamento a livello di codice è utile per evitare le penalizzazioni delle prestazioni con il ridimensionamento continuo. È inoltre utile fornire dimensioni iniziali per righe, colonne e intestazioni ridimensionabili dall'utente e per la modalità di riempimento delle colonne.  
  
 In genere i metodi di ridimensionamento a livello di codice vengono chiamati in momenti specifici. Ad esempio, è possibile ridimensionare a livello di codice tutte le colonne immediatamente dopo il caricamento dei dati oppure è possibile ridimensionare una riga specifica a livello di codice dopo la modifica di un determinato valore di cella.  
  
## <a name="customizing-content-based-sizing-behavior"></a>Personalizzazione del comportamento di ridimensionamento basato sul contenuto  
 È possibile personalizzare i comportamenti di ridimensionamento quando si <xref:System.Windows.Forms.DataGridView> utilizzano i tipi di cella, riga e colonna derivati <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>eseguendo l' <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> override dei metodi, o oppure chiamando gli overload del <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>metodo di ridimensionamento <xref:System.Windows.Forms.DataGridView> protetti in un oggetto derivato controllo. Gli overload del metodo di ridimensionamento protetti sono progettati per funzionare in coppie per ottenere un rapporto ideale tra altezza e larghezza delle celle, evitando le celle eccessivamente ampie o alte. Se ad esempio si chiama `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` l'overload <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> del metodo e si `false` passa un valore per il <xref:System.Boolean> parametro, l'overload calcolerà le altezze e le larghezze ideali per le celle nella riga, ma modificherà l'altezza delle righe. solo. È quindi necessario chiamare il <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> metodo per regolare la larghezza delle colonne in modo che sia la soluzione ideale calcolata.  
  
## <a name="content-based-sizing-options"></a>Opzioni di ridimensionamento basate sul contenuto  
 Le enumerazioni utilizzate dalle proprietà e dai metodi di ridimensionamento hanno valori simili per il dimensionamento basato sul contenuto. Con questi valori, è possibile limitare le celle utilizzate per calcolare le dimensioni preferite. Per tutte le enumerazioni di ridimensionamento, i valori con nomi che fanno riferimento alle celle visualizzate limitano i calcoli alle celle nelle righe visualizzate. Escludere le righe è utile per evitare una riduzione delle prestazioni quando si lavora con una grande quantità di righe. È anche possibile limitare i calcoli ai valori delle celle nelle celle dell'intestazione o non del titolo.  
  
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
- [Procedura: Impostare le modalità di ridimensionamento del controllo Windows Forms DataGridView](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
