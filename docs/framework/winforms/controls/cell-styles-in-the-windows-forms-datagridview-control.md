---
title: Stili della cella nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: a22fc29d2cab21977c0411a440b847b426fb5915
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712279"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Stili della cella nel controllo DataGridView Windows Form
Ogni cella all'interno di <xref:System.Windows.Forms.DataGridView> controllo può avere il proprio stile di visualizzazione, ad esempio il formato di testo, colore di sfondo, colore di primo piano e del tipo di carattere. In genere, tuttavia, più celle condivideranno le caratteristiche di stile specifico.  
  
 Gruppi di celle che condividono gli stili possono includere tutte le celle all'interno di righe particolari o colonne, tutte le celle che contengono determinati valori o tutte le celle nel controllo. Poiché questi gruppi si sovrappongono, ogni cella può ottenere le informazioni di stile da più di un'unica posizione. Ad esempio, è possibile in tutte le celle un <xref:System.Windows.Forms.DataGridView> controllo usare stesso carattere, ma solo le celle delle colonne di tipo valuta per usare il formato di valuta e solo le celle di valuta con i numeri negativi per usare un colore di primo piano rosso.  
  
## <a name="the-datagridviewcellstyle-class"></a>La classe DataGridViewCellStyle  
 Il <xref:System.Windows.Forms.DataGridViewCellStyle> classe contiene le seguenti proprietà correlate allo stile di visualizzazione:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Questa classe contiene inoltre le proprietà seguenti relative alla formattazione:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Per altre informazioni su queste proprietà e altre proprietà di stile di cella, vedere il <xref:System.Windows.Forms.DataGridViewCellStyle> documentazione di riferimento e gli argomenti elencati nella sezione Vedere anche seguente.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Utilizzo di oggetti DataGridViewCellStyle  
 È possibile recuperare <xref:System.Windows.Forms.DataGridViewCellStyle> da diverse proprietà di oggetti di <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, e <xref:System.Windows.Forms.DataGridViewCell> classi e le relative classi derivate. Se una di queste proprietà non è ancora stata impostata, recuperarne il valore verrà creata una nuova <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto. È possibile anche creare un'istanza propria <xref:System.Windows.Forms.DataGridViewCellStyle> degli oggetti e assegnarli a queste proprietà.  
  
 È possibile evitare la duplicazione non necessaria delle informazioni di stile condividendo <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti tra più <xref:System.Windows.Forms.DataGridView> elementi. Poiché gli stili di impostare il controllo, colonna e riga i livelli di filtrare attraverso ogni livello a livello di cella, è anche possibile evitare la duplicazione di stile, impostando soltanto le proprietà di stile a ogni livello che differiscono dai livelli sopra. Questa procedura è descritta più dettagliatamente nella sezione sull'ereditarietà degli stili di seguito.  
  
 Nella tabella seguente sono elencate le proprietà principali che impostano oppure ottengono <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti.  
  
|Proprietà|Classi|Descrizione|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>e le classi derivate|Ottiene o imposta gli stili predefiniti usati da tutte le celle nell'intero controllo (incluse le celle di intestazione), in una colonna o in una riga.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti per tutte le righe nel controllo. Non sono incluse le celle di intestazione.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefinito usati se si passa alternativamente le righe nel controllo. Utilizzato per creare un effetto simile al ledger.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili predefiniti utilizzati dalle intestazioni di riga del controllo. Sottoposto a override dal tema corrente se gli stili di visualizzazione sono abilitati.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili predefiniti utilizzati dalle intestazioni di colonna del controllo. Sottoposto a override dal tema corrente se gli stili di visualizzazione sono abilitati.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> e le classi derivate|Ottiene o imposta gli stili specificati a livello di cella. Questi stili di eseguire l'override di quelle ereditate dai livelli superiori.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>e le classi derivate|Ottiene tutti gli stili attualmente applicati alla cella, riga o colonna, inclusi gli stili ereditati dai livelli superiori.|  
  
 Come già detto, ottenere il valore di una proprietà di stile automaticamente crea un'istanza di un nuovo <xref:System.Windows.Forms.DataGridViewCellStyle> dell'oggetto se la proprietà non è stata precedentemente impostata. Per evitare di creare inutilmente questi oggetti, le classi di riga e colonna hanno una <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> proprietà che è possibile esaminare per determinare se il <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> proprietà è stata impostata. Analogamente, le classi di cella hanno una <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> proprietà che indica se il <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà è stata impostata.  
  
 Ognuna delle proprietà di stile ha come corrispondente *PropertyName* `Changed` evento sul <xref:System.Windows.Forms.DataGridView> controllo. Per righe, colonne e le proprietà di cella, il nome dell'evento inizia con "`Row`","`Column`", o "`Cell`" (ad esempio, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Ciascuno di questi eventi si verifica quando la proprietà di stile di visualizzazione corrispondente è impostata su un valore differente <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto. Questi eventi non si verificano quando si recupera un <xref:System.Windows.Forms.DataGridViewCellStyle> da una proprietà di stile dell'oggetto e modificare i valori delle proprietà. Per rispondere alle modifiche apportate agli oggetti stile cella, gestire il <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> evento.  
  
## <a name="style-inheritance"></a>Ereditarietà degli stili  
 Ciascuna <xref:System.Windows.Forms.DataGridViewCell> Ottiene l'aspetto del controllo dal relativo <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà. Il <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da questa proprietà eredita i valori da una gerarchia di proprietà del tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Queste proprietà sono elencate di seguito nell'ordine in cui il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> per le celle di intestazione non ottiene i relativi valori.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo per le celle nelle righe con numeri di indice dispari)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per le celle dell'intestazione di riga e colonna, il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà viene popolata dai valori nell'elenco seguente di proprietà di origine nell'ordine indicato.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Il diagramma seguente illustra questo processo.  
  
 ![Le proprietà di tipo DataGridViewCellStyle](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells diagramma di ereditarietà")  
  
 È possibile accedere anche gli stili ereditati da colonne e righe specifiche. La colonna <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> proprietà eredita i valori dalle proprietà seguenti.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La riga <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> proprietà eredita i valori dalle proprietà seguenti.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (solo per le celle nelle righe con numeri di indice dispari)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per ogni proprietà in una <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da un' `InheritedStyle` proprietà, il valore della proprietà viene ottenuto dallo stile della cella prima nell'elenco appropriato che dispone della corrispondente proprietà impostata su un valore diverso dal <xref:System.Windows.Forms.DataGridViewCellStyle> classe valori predefiniti.  
  
 Nella tabella seguente viene illustrato come il <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> valore della proprietà per una cella di esempio viene ereditato dalla relativa colonna che lo contiene.  
  
|proprietà di tipo `DataGridViewCellStyle`|Esempio `ForeColor` valore per l'oggetto recuperato|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In questo caso, il <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> valore dalla riga della cella è il primo valore reale nell'elenco. Questo diventa il <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> ha valore della cella <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 Il diagramma seguente illustra come i vari <xref:System.Windows.Forms.DataGridViewCellStyle> proprietà possono ereditare i relativi valori da posizioni diverse.  
  
 ![Proprietà DataGridView&#45;ereditarietà del valore](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells diagramma di ereditarietà di valore")  
  
 Sfruttando l'ereditarietà dello stile, è possibile fornire stili appropriati per l'intero controllo senza la necessità di specificare le stesse informazioni in più posizioni.  
  
 Anche se le celle di intestazione fa parte di ereditarietà degli stili come descritto, gli oggetti restituiti dai <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> proprietà del <xref:System.Windows.Forms.DataGridView> controllo dispone di valori di proprietà iniziali che sostituiscono i valori delle proprietà dell'oggetto restituito da il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà. Se si desidera che le proprietà impostate per l'oggetto restituito dal <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà da applicare alle intestazioni di riga e colonna, è necessario impostare le proprietà corrispondenti di oggetti restituiti dai <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> indicate le proprietà sui valori predefiniti per il <xref:System.Windows.Forms.DataGridViewCellStyle> classe.  
  
> [!NOTE]
>  Se sono abilitati gli stili di visualizzazione, le intestazioni di riga e colonna (tranne che per il <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) vengono automaticamente uno stile che riflette il tema corrente, si esegue l'override di tutti gli stili specificati da queste proprietà.  
  
 Il <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, e <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> inizializzano anche alcuni valori dell'oggetto restituito dalla colonna <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà. Per altre informazioni, vedere la documentazione di riferimento per questi tipi.  
  
## <a name="setting-styles-dynamically"></a>Impostazione degli stili in modo dinamico  
 Per personalizzare gli stili delle celle con determinati valori, implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. Gestori per questo evento ricevono un argomento del <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> tipo. Questo oggetto contiene le proprietà che consentono di determinare il valore della cella formattato con relativa posizione all'interno di <xref:System.Windows.Forms.DataGridView> controllo. Questo oggetto contiene anche un <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> che viene inizializzato al valore della proprietà di <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà della cella in corso di formattazione. È possibile modificare le proprietà di stile di cella per specificare le informazioni sullo stile appropriate per il valore di cella e il percorso.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventi ricevono inoltre un <xref:System.Windows.Forms.DataGridViewCellStyle> dati dell'evento dell'oggetto, ma in maiuscole, è una copia della riga <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> proprietà per scopi di sola lettura e modifica non influisce sul controllo.  
  
 È inoltre possibile modificare dinamicamente gli stili delle singole celle in risposta a eventi, ad esempio la <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.CellMouseLeave> eventi. Ad esempio, in un gestore per il <xref:System.Windows.Forms.DataGridView.CellMouseEnter> evento, è possibile archiviare il valore corrente del colore di sfondo della cella (recuperati tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà), quindi impostarlo su un nuovo colore che viene evidenziata la cella quando il mouse viene posizionato su di esso. In un gestore per il <xref:System.Windows.Forms.DataGridView.CellMouseLeave> evento, è quindi possibile ripristinare il colore di sfondo per il valore originale.  
  
> [!NOTE]
>  La memorizzazione nella cache i valori archiviati della cella <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà è importante indipendentemente dall'impostazione di un valore di stile di visualizzazione particolare. Se si sostituisce temporaneamente un'impostazione di stile, ripristinarlo allo stato originale "non impostato" assicura che la cella tornerà a ereditare l'impostazione di stile da un livello superiore. Se è necessario determinare lo stile effettivo in vigore per una cella indipendentemente dal fatto che lo stile è ereditato, utilizzare la cella <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà.  
  
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
- [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Formattazione di dati nel controllo DataGridView di Windows Form](data-formatting-in-the-windows-forms-datagridview-control.md)
