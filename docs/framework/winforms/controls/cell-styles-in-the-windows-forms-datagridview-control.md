---
title: Stili della cella nel controllo DataGridView Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 915aba380b6fe35299de94720f216cda5ab66721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Stili della cella nel controllo DataGridView Windows Form
Ogni cella all'interno di <xref:System.Windows.Forms.DataGridView> controllo può disporre di uno stile specifico, ad esempio il formato di testo, colore di sfondo, colore di primo piano e tipo di carattere. In genere, tuttavia, più celle condividono le caratteristiche di stile particolare.  
  
 Gruppi di celle che condividono gli stili possono includere tutte le celle all'interno di righe specifiche o colonne, tutte le celle che contengono determinati valori o tutte le celle nel controllo. Poiché questi gruppi si sovrappongono, ogni cella può ottenere le informazioni di stile da più di un'unica posizione. Ad esempio, è consigliabile ogni cella un <xref:System.Windows.Forms.DataGridView> controllo da utilizzare stesso carattere, ma solo le celle delle colonne di valuta da utilizzare il formato di valuta e solo le celle di valuta con numeri negativi per utilizzare un colore di primo piano rosso.  
  
## <a name="the-datagridviewcellstyle-class"></a>La classe DataGridViewCellStyle  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> classe contiene le seguenti proprietà correlate allo stile di visualizzazione:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 Questa classe contiene inoltre le proprietà seguenti relative alla formattazione:  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> e <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 Per ulteriori informazioni su queste proprietà e altre proprietà di stile di cella, vedere il <xref:System.Windows.Forms.DataGridViewCellStyle> documentazione di riferimento e gli argomenti elencati nella sezione Vedere anche.  
  
## <a name="using-datagridviewcellstyle-objects"></a>Utilizzo di oggetti DataGridViewCellStyle  
 È possibile recuperare <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti da varie proprietà del <xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>, e <xref:System.Windows.Forms.DataGridViewCell> classi e le relative classi derivate. Se una di queste proprietà non è ancora stata impostata, recuperarne il valore verrà creato un nuovo <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto. È inoltre possibile creare istanze proprie <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti e assegnarli a queste proprietà.  
  
 È possibile evitare un'inutile duplicazione delle informazioni di stile tramite la condivisione <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti tra più <xref:System.Windows.Forms.DataGridView> elementi. Poiché gli stili impostati al controllo, una colonna e un filtro per i livelli di riga verso il basso attraverso ogni livello a livello di cella, è anche possibile evitare la duplicazione di stile impostando solo le proprietà di stile a ogni livello che sono diversi rispetto ai livelli superiori. Come descritto più dettagliatamente nella sezione sull'ereditarietà degli stili di seguito.  
  
 Nella tabella seguente sono elencate le proprietà principali che ottiene o imposta un <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti.  
  
|Proprietà|Classi|Descrizione|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>, <xref:System.Windows.Forms.DataGridViewColumn>, <xref:System.Windows.Forms.DataGridViewRow>e le classi derivate|Ottiene o imposta gli stili predefiniti utilizzati da tutte le celle nell'intero controllo (incluse le celle di intestazione), in una colonna o in una riga.|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefiniti per tutte le righe nel controllo. Non include le celle di intestazione.|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili di cella predefinito utilizzati da righe alternate nel controllo. Consente di creare un effetto registro.|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili predefiniti utilizzati dalle intestazioni di riga del controllo. Se sono abilitati, sottoposto a override dal tema corrente.|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|Ottiene o imposta gli stili predefiniti utilizzati dalle intestazioni di colonna del controllo. Se sono abilitati, sottoposto a override dal tema corrente.|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell>e le classi derivate|Ottiene o imposta gli stili specificati a livello di cella. Questi stili sostituiscono quelli ereditati dai livelli superiori.|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewRow>, <xref:System.Windows.Forms.DataGridViewColumn>e le classi derivate|Ottiene tutti gli stili attualmente applicati alla cella, riga o colonna, inclusi gli stili ereditati dai livelli superiori.|  
  
 Come indicato in precedenza, ottenere il valore di una proprietà di stile automaticamente creata un'istanza di un nuovo <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto se la proprietà non è stata precedentemente impostata. Per evitare la creazione di questi oggetti inutilmente, le classi di riga e colonna hanno un <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> proprietà che è possibile verificare per determinare se il <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> proprietà è stata impostata. Analogamente, le classi di cella hanno un <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> proprietà che indica se il <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà è stata impostata.  
  
 Ogni proprietà di stile ha un corrispondente *PropertyName* `Changed` evento il <xref:System.Windows.Forms.DataGridView> controllo. Per riga, colonna e le proprietà di cella, il nome dell'evento inizia con "`Row`","`Column`", o "`Cell`" (ad esempio, <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>). Ciascuno di questi eventi si verifica quando la proprietà di stile corrispondente è impostata su un altro <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto. Questi eventi non si verificano quando si recupera un <xref:System.Windows.Forms.DataGridViewCellStyle> da una proprietà di stile dell'oggetto e modificare i valori delle proprietà. Per rispondere alle modifiche apportate agli oggetti di stile di cella stessi, gestire il <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> evento.  
  
## <a name="style-inheritance"></a>Ereditarietà degli stili  
 Ogni <xref:System.Windows.Forms.DataGridViewCell> Ottiene il relativo aspetto dalla relativa <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà. Il <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da questa proprietà eredita i valori da una gerarchia di proprietà del tipo <xref:System.Windows.Forms.DataGridViewCellStyle>. Queste proprietà sono elencate di seguito nell'ordine in cui il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> per le celle di intestazione non ottiene i valori.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo per le celle delle righe con numeri di indice dispari)  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per le celle dell'intestazione di riga e colonna, il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà viene popolata dai valori nell'elenco seguente delle proprietà di origine nell'ordine indicato.  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Nel diagramma seguente viene illustrato questo processo.  
  
 ![Proprietà di tipo DataGridViewCellStyle](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 È inoltre possibile accedere agli stili ereditati da colonne e righe specifiche. La colonna <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> proprietà eredita i valori dalle proprietà seguenti.  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 La riga <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> proprietà eredita i valori dalle proprietà seguenti.  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>(solo per le celle delle righe con numeri di indice dispari)  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Per ogni proprietà in un <xref:System.Windows.Forms.DataGridViewCellStyle> oggetto restituito da un `InheritedStyle` proprietà, il valore della proprietà viene ottenuto dal primo stile di cella nell'elenco appropriato che dispone della corrispondente proprietà impostata su un valore diverso dal <xref:System.Windows.Forms.DataGridViewCellStyle> classe delle impostazioni predefinite.  
  
 Nella tabella seguente viene illustrato come la <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> ereditato la colonna contenente il valore della proprietà per una cella di esempio.  
  
|Proprietà di tipo`DataGridViewCellStyle`|Esempio `ForeColor` valore per l'oggetto recuperato|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 In questo caso, il <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> valore dalla riga della cella è il primo valore effettivo nell'elenco. Questo valore diventa il <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> valore della proprietà della cella <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>.  
  
 Il diagramma seguente illustra come i diversi <xref:System.Windows.Forms.DataGridViewCellStyle> proprietà possono ereditare i relativi valori da posizioni diverse.  
  
 ![DataGridView ereditarietà del valore di proprietà &#45;](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 Sfruttando di ereditarietà, è possibile fornire stili appropriati per l'intero controllo senza dover specificare le stesse informazioni in più posizioni.  
  
 Anche se le celle di intestazione partecipano all'ereditarietà stile come descritto, gli oggetti restituiti dal <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> le proprietà del <xref:System.Windows.Forms.DataGridView> controllo dispone di valori iniziali delle proprietà che sostituiscono i valori delle proprietà dell'oggetto restituito da il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà. Se si desidera che le proprietà impostate per l'oggetto restituito dal <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> proprietà da applicare alle intestazioni di riga e colonna, è necessario impostare le proprietà corrispondenti di oggetti restituiti dal <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> indicato sui valori predefiniti per la <xref:System.Windows.Forms.DataGridViewCellStyle> classe.  
  
> [!NOTE]
>  Se sono abilitati gli stili di visualizzazione, le intestazioni di riga e colonna (tranne che per il <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) viene automaticamente applicato uno stile dal tema corrente, si esegue l'override di tutti gli stili specificati mediante queste proprietà.  
  
 Il <xref:System.Windows.Forms.DataGridViewButtonColumn>, <xref:System.Windows.Forms.DataGridViewImageColumn>, e <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> inizializzano inoltre alcuni valori dell'oggetto restituito dalla colonna <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà. Per ulteriori informazioni, vedere la documentazione di riferimento per questi tipi.  
  
## <a name="setting-styles-dynamically"></a>L'impostazione degli stili in modo dinamico  
 Per personalizzare gli stili di celle con valori particolari, implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. Gestori per questo evento ricevono un argomento del <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> tipo. Questo oggetto contiene proprietà che consentono di determinare il valore della cella formattato con la posizione nel <xref:System.Windows.Forms.DataGridView> controllo. Questo oggetto contiene inoltre un <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> proprietà che viene inizializzato il valore di <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà della cella formattata. È possibile modificare le proprietà di stile di cella per specificare le informazioni di stile appropriate per il valore di cella e il percorso.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventi ricevono inoltre un <xref:System.Windows.Forms.DataGridViewCellStyle> dati dell'evento dell'oggetto, ma in maiuscole, è una copia della riga <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> proprietà ai fini di sola lettura e modifiche non influiscono sul controllo.  
  
 È inoltre possibile modificare dinamicamente gli stili delle singole celle in risposta a eventi, ad esempio il <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.CellMouseLeave> eventi. Ad esempio, in un gestore per il <xref:System.Windows.Forms.DataGridView.CellMouseEnter> evento, è possibile archiviare il valore del colore di sfondo della cella corrente (recuperati tramite la cella <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà), quindi viene impostato un nuovo colore che la cella viene evidenziata quando il mouse viene spostato su di esso. In un gestore per il <xref:System.Windows.Forms.DataGridView.CellMouseLeave> evento, è quindi possibile ripristinare il colore di sfondo per il valore originale.  
  
> [!NOTE]
>  La memorizzazione nella cache i valori archiviati nella cella <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà è importante indipendentemente dall'impostazione di un valore di stile particolare. Se si sostituisce temporaneamente un'impostazione di stile, eseguire il ripristino allo stato "non impostata" originale garantisce che la cella tornerà a ereditare l'impostazione di stile da un livello superiore. Se è necessario determinare lo stile effettivo per una cella, indipendentemente dal fatto se lo stile è ereditato, utilizzare la cella <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Formattazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
