---
title: Stili della cella nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: be4c47db5c56685a84153a9ae4a9a2fe14c6adad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917764"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Stili della cella nel controllo DataGridView Windows Form
Ogni cella all'interno <xref:System.Windows.Forms.DataGridView> del controllo può avere un proprio stile, ad esempio il formato del testo, il colore di sfondo, il colore di primo piano e il tipo di carattere. In genere, tuttavia, più celle condividono particolari caratteristiche di stile.  
  
 I gruppi di celle che condividono stili possono includere tutte le celle all'interno di righe o colonne specifiche, tutte le celle che contengono valori specifici o tutte le celle del controllo. Poiché questi gruppi si sovrappongono, ogni cella può ottenere le informazioni di stile da più di una posizione. È possibile, ad esempio, che tutte le celle <xref:System.Windows.Forms.DataGridView> di un controllo usino lo stesso tipo di carattere, ma solo le celle nelle colonne di valuta usino il formato di valuta e solo le celle di valuta con numeri negativi usino un colore di primo piano rosso.  
  
## <a name="the-datagridviewcellstyle-class"></a>Classe DataGridViewCellStyle  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> classe contiene le seguenti proprietà correlate allo stile di visualizzazione:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Questa classe contiene inoltre le seguenti proprietà correlate alla formattazione:  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Per ulteriori informazioni su queste proprietà e altre proprietà di tipo cella, vedere la <xref:System.Windows.Forms.DataGridViewCellStyle> documentazione di riferimento e gli argomenti elencati nella sezione vedere anche di seguito.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Uso di oggetti DataGridViewCellStyle  
 È possibile recuperare <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti da diverse proprietà <xref:System.Windows.Forms.DataGridView>delle classi, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>e <xref:System.Windows.Forms.DataGridViewCell> e dalle relative classi derivate. Se una di queste proprietà non è ancora stata impostata, il recupero del relativo valore creerà un nuovo <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto. È anche possibile creare un'istanza di <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti personalizzati e assegnarli a queste proprietà.  
  
 È possibile evitare la duplicazione non necessaria delle informazioni <xref:System.Windows.Forms.DataGridViewCellStyle> di stile condividendo gli oggetti tra più <xref:System.Windows.Forms.DataGridView> elementi. Poiché gli stili impostati a livello di controllo, colonna e riga filtrano ogni livello a livello di cella, è anche possibile evitare la duplicazione dello stile impostando solo le proprietà di stile a ogni livello che differiscono dai livelli precedenti. Questa operazione viene descritta più dettagliatamente nella sezione relativa all'ereditarietà dello stile riportata di seguito.  
  
 Nella tabella seguente sono elencate le proprietà primarie che ottengono <xref:System.Windows.Forms.DataGridViewCellStyle> o impostano oggetti.  
  
|Proprietà|Classi|Descrizione|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>classi derivate, <xref:System.Windows.Forms.DataGridViewColumn>,e <xref:System.Windows.Forms.DataGridViewRow>|Ottiene o imposta gli stili predefiniti utilizzati da tutte le celle nell'intero controllo (incluse le celle di intestazione), in una colonna o in una riga.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti utilizzati da tutte le righe nel controllo. Non sono incluse le celle di intestazione.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti utilizzati dalle righe alternate nel controllo. Utilizzato per creare un effetto di tipo Ledger.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti utilizzati dalle intestazioni di riga del controllo. Sottoposto a override dal tema corrente se gli stili di visualizzazione sono abilitati.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti utilizzati dalle intestazioni di colonna del controllo. Sottoposto a override dal tema corrente se gli stili di visualizzazione sono abilitati.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell>classi derivate e|Ottiene o imposta gli stili specificati a livello di cella. Questi stili eseguono l'override di quelli ereditati dai livelli superiori.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>classi derivate, <xref:System.Windows.Forms.DataGridViewRow>,e <xref:System.Windows.Forms.DataGridViewColumn>|Ottiene tutti gli stili attualmente applicati alla cella, alla riga o alla colonna, inclusi gli stili ereditati dai livelli più alti.|  
  
 Come indicato in precedenza, il recupero del valore di una proprietà di stile crea automaticamente <xref:System.Windows.Forms.DataGridViewCellStyle> un'istanza di un nuovo oggetto se la proprietà non è stata impostata in precedenza. Per evitare di creare questi oggetti inutilmente, le classi Row e Column hanno <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> una proprietà che è possibile verificare per determinare se <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> la proprietà è stata impostata. Analogamente, le classi di celle <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> hanno una proprietà che indica <xref:System.Windows.Forms.DataGridViewCell.Style%2A> se la proprietà è stata impostata.  
  
 Ogni proprietà di stile ha un evento *PropertyName* `Changed` corrispondente sul <xref:System.Windows.Forms.DataGridView> controllo. Per le proprietà di riga, colonna e cella, il nome dell'evento inizia con "`Row`", "`Column`" o "`Cell`" (ad esempio, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Ognuno di questi eventi si verifica quando la proprietà Style corrispondente è impostata su un <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto diverso. Questi eventi non si verificano quando si recupera <xref:System.Windows.Forms.DataGridViewCellStyle> un oggetto da una proprietà di stile e si modificano i valori delle relative proprietà. Per rispondere alle modifiche apportate agli oggetti di stile della cella <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> , gestire l'evento.  
  
## <a name="style-inheritance"></a>Ereditarietà degli stili  
 Ognuno <xref:System.Windows.Forms.DataGridViewCell> ottiene il proprio aspetto dalla <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> relativa proprietà. L' <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da questa proprietà eredita i valori da una gerarchia di proprietà di tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Queste proprietà sono elencate di seguito nell'ordine in cui l' <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> oggetto per le celle non di intestazione ottiene i valori.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo per le celle nelle righe con numeri di indice dispari)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per le celle delle intestazioni di riga e <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> di colonna, la proprietà viene popolata dai valori dell'elenco seguente di proprietà di origine nell'ordine specificato.  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Il diagramma seguente illustra questo processo.  
  
 ![Proprietà di tipo DataGridViewCellStyle](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "Diagramma di ereditarietà dataGridViewCells")  
  
 È anche possibile accedere agli stili ereditati da righe e colonne specifiche. La proprietà <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> Column eredita i valori dalle proprietà seguenti.  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La proprietà <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> Row eredita i valori dalle proprietà seguenti.  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo per le celle nelle righe con numeri di indice dispari)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per ogni proprietà in un <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da una `InheritedStyle` proprietà, il valore della proprietà viene ottenuto dal primo stile della cella nell'elenco appropriato la cui proprietà corrispondente è impostata su un valore diverso da quello <xref:System.Windows.Forms.DataGridViewCellStyle> predefinito della classe.  
  
 Nella tabella seguente viene illustrato il modo <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> in cui il valore della proprietà per una cella di esempio viene ereditato dalla colonna che lo contiene.  
  
|Proprietà di tipo`DataGridViewCellStyle`|Valore `ForeColor` di esempio per l'oggetto recuperato|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In questo caso, il <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> valore della riga della cella è il primo valore reale nell'elenco. Che diventa il <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> valore della proprietà della <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>cella.  
  
 Il diagramma seguente illustra il modo in <xref:System.Windows.Forms.DataGridViewCellStyle> cui le diverse proprietà possono ereditare i valori da posizioni diverse.  
  
 ![Ereditarietà del&#45;valore della proprietà DataGridView](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "Diagramma di ereditarietà del valore") di dataGridViewCells  
  
 Sfruttando l'ereditarietà dello stile, è possibile fornire stili appropriati per l'intero controllo senza dover specificare le stesse informazioni in più posizioni.  
  
 Sebbene le celle di intestazione partecipino all'ereditarietà dello stile come descritto, gli <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> oggetti <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> restituiti dalle proprietà <xref:System.Windows.Forms.DataGridView> e del controllo hanno valori iniziali di proprietà che eseguono l'override dei valori delle proprietà dell'oggetto restituito da <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà. Se si desidera che le proprietà impostate per l'oggetto restituito dalla <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà vengano applicate alle intestazioni di riga e di colonna, è necessario impostare le proprietà corrispondenti degli oggetti restituiti <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> dalle proprietà <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> e sui valori predefiniti indicati. per la <xref:System.Windows.Forms.DataGridViewCellStyle> classe.  
  
> [!NOTE]
> Se gli stili di visualizzazione sono abilitati, le intestazioni di riga e di <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>colonna (ad eccezione di) vengono automaticamente impostate in base al tema corrente, eseguendo l'override degli stili specificati da queste proprietà.  
  
 I <xref:System.Windows.Forms.DataGridViewButtonColumn>tipi <xref:System.Windows.Forms.DataGridViewImageColumn>, <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> inizializzano anche alcuni valori dell'oggetto restituito dalla proprietà della colonna. Per ulteriori informazioni, vedere la documentazione di riferimento per questi tipi.  
  
## <a name="setting-styles-dynamically"></a>Impostazione dinamica degli stili  
 Per personalizzare gli stili delle celle con determinati valori, implementare un gestore per l' <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. I <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> gestori per questo evento ricevono un argomento del tipo. Questo oggetto contiene proprietà che consentono di determinare il valore della cella da formattare insieme alla relativa posizione nel <xref:System.Windows.Forms.DataGridView> controllo. Questo oggetto contiene inoltre una <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> proprietà inizializzata sul valore <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> della proprietà della cella in corso di formattazione. È possibile modificare le proprietà di stile della cella per specificare le informazioni di stile appropriate per il valore e la posizione della cella.  
  
> [!NOTE]
> Gli <xref:System.Windows.Forms.DataGridView.RowPrePaint> eventi <xref:System.Windows.Forms.DataGridView.RowPostPaint> e ricevono anche un <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto nei dati dell'evento, ma in questo caso si tratta di una copia della proprietà Row <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> per finalità di sola lettura e le modifiche apportate non influiscono sul controllo.  
  
 È anche possibile modificare dinamicamente gli stili delle singole celle in risposta a eventi quali gli <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> eventi e. <xref:System.Windows.Forms.DataGridView.CellMouseLeave> Ad esempio, in un gestore per l' <xref:System.Windows.Forms.DataGridView.CellMouseEnter> evento, è possibile archiviare il valore corrente del colore di sfondo della cella (recuperato tramite la <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà della cella), quindi impostarlo su un nuovo colore che evidenzierà la cella quando il mouse viene spostato su di esso. In un gestore per l' <xref:System.Windows.Forms.DataGridView.CellMouseLeave> evento, è possibile ripristinare il colore di sfondo al valore originale.  
  
> [!NOTE]
> La memorizzazione nella cache dei valori archiviati nella <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà della cella è importante, indipendentemente dal fatto che sia impostato un particolare valore di stile. Se si sostituisce temporaneamente un'impostazione di stile, il ripristino dello stato originale "non impostato" garantisce che la cella torni a ereditare l'impostazione di stile da un livello superiore. Se è necessario determinare lo stile effettivo attivo per una cella indipendentemente dal fatto che lo stile venga ereditato, utilizzare la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà della cella.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare gli stili di cella predefiniti per il controllo DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
