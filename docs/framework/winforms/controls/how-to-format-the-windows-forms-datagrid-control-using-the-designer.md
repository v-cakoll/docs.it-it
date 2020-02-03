---
title: Formattare il controllo DataGrid usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: 548acac0fc7724490bfe89927ec0662b3488c230
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736800"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: formattare il controllo DataGrid Windows Form mediante la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

L'applicazione di colori diversi a diverse parti di un controllo <xref:System.Windows.Forms.DataGrid> può contribuire a rendere le informazioni più facili da leggere e interpretare. Il colore può essere applicato a righe e colonne. Le righe e le colonne possono anche essere nascoste o visualizzate a propria discrezione.

La formattazione del controllo <xref:System.Windows.Forms.DataGrid> è costituita da tre aspetti di base:

- È possibile impostare le proprietà per stabilire uno stile predefinito in cui vengono visualizzati i dati.

- Da tale base è quindi possibile personalizzare la modalità di visualizzazione di determinate tabelle in fase di esecuzione.

- Infine, è possibile modificare le colonne visualizzate nella griglia dei dati, nonché i colori e altre formattazioni visualizzate.

Come passaggio iniziale per la formattazione di una griglia di dati, è possibile impostare le proprietà del <xref:System.Windows.Forms.DataGrid> stesso. Queste scelte di colore e formato costituiscono una base da cui è possibile apportare modifiche in base alle tabelle e alle colonne di dati visualizzate.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGrid>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, per impostazione predefinita, il controllo <xref:System.Windows.Forms.DataGrid> non è presente nella **casella degli strumenti** . Per altre informazioni, vedere [procedura: aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid

1. Selezionare il controllo <xref:System.Windows.Forms.DataGrid>.

2. Nella finestra **Proprietà** impostare le proprietà seguenti, a seconda dei casi.

    |Proprietà|Descrizione|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La proprietà `BackColor` definisce il colore delle righe pari della griglia. Quando si imposta la proprietà <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> su un colore diverso, ogni altra riga viene impostata sul nuovo colore (righe 1, 3, 5 e così via).|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre le proprietà <xref:System.Windows.Forms.DataGrid.BackColor%2A> e <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> determinano il colore delle righe nella griglia, la proprietà <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> determina il colore dell'area al di fuori dell'area riga, che è visibile solo quando la griglia viene spostata alla fine o se nella griglia sono contenute solo poche righe.|
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Stile del bordo della griglia, uno dei valori di enumerazione <xref:System.Windows.Forms.BorderStyle>.|
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Colore di sfondo della didascalia della finestra della griglia visualizzata immediatamente sopra la griglia.|
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Il tipo di carattere della didascalia nella parte superiore della griglia.|
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Colore di sfondo della didascalia della finestra della griglia.|
    |<xref:System.Windows.Forms.Control.Font%2A>|Tipo di carattere utilizzato per visualizzare il testo nella griglia.|
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Colore del tipo di carattere visualizzato dai dati nelle righe della griglia dei dati.|
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Colore delle linee della griglia dei dati.|
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Stile delle linee che separano le celle della griglia, uno dei valori di enumerazione <xref:System.Windows.Forms.DataGridLineStyle>.|
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Colore di sfondo delle intestazioni di riga e colonna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Tipo di carattere utilizzato per le intestazioni di colonna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione di colonna e il segno più (+) e i glifi del segno meno (-) che espandono e comprimono le righe quando vengono visualizzate più tabelle correlate.|
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Colore del testo di tutti i collegamenti nella griglia dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In una tabella figlio si tratta del colore di sfondo delle righe padre.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In una tabella figlio si tratta del colore di primo piano delle righe padre.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina se i nomi della tabella e della colonna vengono visualizzati nella riga padre, per mezzo dell'enumerazione <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Larghezza predefinita (in pixel) delle colonne della griglia. Impostare questa proprietà prima di reimpostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A>, separatamente o tramite il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>, oppure la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Altezza della riga, in pixel, delle righe della griglia. Impostare questa proprietà prima di reimpostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A>, separatamente o tramite il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>, oppure la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Larghezza delle intestazioni di riga della griglia.|
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Quando si seleziona una riga o una cella, si tratta del colore di sfondo.|
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Quando si seleziona una riga o una cella, questo è il colore di primo piano.|

    > [!NOTE]
    > Quando si personalizzano i colori dei controlli, è possibile rendere il controllo inaccessibile a causa di una scelta di colori insufficiente (ad esempio, rosso e verde). Usare i colori disponibili nella tavolozza **colori di sistema** per evitare questo problema.

    Per la procedura seguente è necessario un controllo <xref:System.Windows.Forms.DataGrid> associato a una tabella di dati. Per altre informazioni, vedere [procedura: associare il controllo DataGrid Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Per impostare lo stile della tabella e della colonna di una tabella dati in fase di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.DataGrid> sul form.

2. Nella finestra **Proprietà** selezionare la proprietà <xref:System.Windows.Forms.DataGrid.TableStyles%2A> e fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)).

3. Nella finestra di dialogo **Editor della raccolta DataGridTableStyle** fare clic su **Aggiungi** per aggiungere uno stile tabella alla raccolta.

     Con l' **Editor della raccolta DataGridTableStyle**è possibile aggiungere e rimuovere gli stili di tabella, impostare le proprietà di visualizzazione e layout e impostare il nome del mapping per gli stili di tabella.

4. Impostare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> sul nome del mapping per ogni stile di tabella.

     Il nome del mapping viene utilizzato per specificare lo stile della tabella da utilizzare con la tabella.

5. Nell' **Editor della raccolta DataGridTableStyle**selezionare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> e fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nel finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)).

6. Nella finestra di dialogo **Editor della raccolta DataGridColumnStyle** aggiungere gli stili delle colonne allo stile di tabella creato.

     Con l' **Editor della raccolta DataGridColumnStyle**è possibile aggiungere e rimuovere gli stili delle colonne, impostare le proprietà di visualizzazione e layout e impostare il nome del mapping e le stringhe di formattazione per le colonne di dati.

    > [!NOTE]
    > Per ulteriori informazioni sulle stringhe di formattazione, vedere [formattazione di tipi](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
