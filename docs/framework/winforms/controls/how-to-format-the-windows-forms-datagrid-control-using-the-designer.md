---
title: 'Procedura: Formattare il controllo di DataGrid Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: 92939f1bdddaca1d743116a4ae4ee9da657abf19
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725363"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Formattare il controllo di DataGrid Windows Form usando la finestra di progettazione

> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Applicazione di colori diversi alle varie parti di un <xref:System.Windows.Forms.DataGrid> il controllo è utile per rendere più semplice da leggere e interpretare le informazioni in esso. Colore può essere applicato alle righe e colonne. Le righe e colonne possono anche essere nascoste o visualizzate a discrezione dell'utente.  
  
 Esistono tre aspetti di base della formattazione di <xref:System.Windows.Forms.DataGrid> controllo:  
  
-   È possibile impostare proprietà per definire uno stile predefinito in cui vengono visualizzati dati.  
  
-   Da quella base, è quindi possibile personalizzare il modo che in fase di esecuzione vengono visualizzate determinate tabelle.  
  
-   Infine, è possibile modificare le colonne da visualizzare nella griglia dei dati, nonché i colori e altro di formattazione che viene visualizzato.  
  
 Come passaggio iniziale in una griglia dei dati di formattazione, è possibile impostare le proprietà del <xref:System.Windows.Forms.DataGrid> stesso. Queste scelte di colori e il formato formano una base da cui è quindi possibile apportare modifiche a seconda delle tabelle di dati e le colonne visualizzate.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005, il <xref:System.Windows.Forms.DataGrid> controllo non è nel **casella degli strumenti** per impostazione predefinita. Per altre informazioni, vedere [Procedura: Aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.DataGrid>.  
  
2.  Nel **proprietà** finestra, impostare le proprietà seguenti, come appropriato.  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Il `BackColor` proprietà definisce il colore delle righe pari della griglia. Quando si imposta il <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà su un colore diverso, tutte le altre righe è impostata su questo nuovo colore (righe 1, 3, 5 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre il <xref:System.Windows.Forms.DataGrid.BackColor%2A> e <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà determina il colore delle righe nella griglia di <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> proprietà determina il colore dell'area all'esterno dell'area riga, che è visibile solo quando la griglia è necessario scorrere verso il basso, o se solo alcune righe siano contenuto della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Stile del bordo della griglia, uno del <xref:System.Windows.Forms.BorderStyle> valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Il colore di sfondo del titolo di finestra della griglia che viene visualizzato immediatamente sopra la griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Il tipo di carattere della didascalia nella parte superiore della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Il colore di sfondo del titolo di finestra della griglia.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Il tipo di carattere utilizzato per visualizzare il testo nella griglia.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Colore del tipo di carattere visualizzato in base ai dati nelle righe della griglia dei dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Il colore delle linee della griglia della griglia dei dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Lo stile delle linee che separano le celle della griglia, uno del <xref:System.Windows.Forms.DataGridLineStyle> valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Il colore di sfondo delle intestazioni di riga e colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Il tipo di carattere utilizzato per le intestazioni di colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Vengono visualizzati il colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione e il segno più (+) e segno meno (-) glifi espandere e comprimere le righe quando più tabelle correlate.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Colore del testo di tutti i collegamenti nella griglia dei dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In una tabella figlio, questo è il colore di sfondo delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In una tabella figlio, questo è il colore di primo piano delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina se i nomi di tabella e di colonna vengono visualizzati nella riga padre, per mezzo del <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Larghezza predefinita (in pixel) delle colonne della griglia. Impostare questa proprietà prima di reimpostare il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> delle proprietà (sia separatamente, o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo), o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|L'altezza di riga, in pixel, delle righe nella griglia. Impostare questa proprietà prima di reimpostare il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> delle proprietà (sia separatamente, o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo), o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|La larghezza delle intestazioni di riga della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Quando una riga o cella è selezionata, questo è il colore di sfondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Quando una riga o cella è selezionata, questo è il colore primo piano.|  
  
    > [!NOTE]
    >  Quando si personalizzano i colori dei controlli, è possibile rendere il controllo inaccessibile a causa di scarsa colore scelto (ad esempio, rosso e verde). Utilizzare i colori disponibili nel **colori di sistema** tavolozza per evitare questo problema.

     La procedura seguente richiede un <xref:System.Windows.Forms.DataGrid> controllo associato a una tabella di dati. Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Per impostare lo stile di tabella e colonna di una tabella di dati in fase di progettazione

1.  Selezionare il <xref:System.Windows.Forms.DataGrid> controllo sul form.

2.  Nel **delle proprietà** finestra, seleziona il <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà e fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png " vbEllipsesButton")) pulsante.

3.  Nel **raccolta DataGridTableStyle** della finestra di dialogo fare clic su **Add** per aggiungere uno stile di tabella all'insieme.

     Con il **raccolta DataGridTableStyle**, è possibile aggiungere e rimuovere gli stili di tabella, impostare la visualizzazione e le proprietà del layout e set il nome di mapping per gli stili di tabella.

4.  Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà sul nome del mapping per ogni stile di tabella.

     Il nome del mapping consente di specificare quali stile di tabella deve essere usato con la tabella.

5.  Nel **raccolta DataGridTableStyle**, selezionare la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà e fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton ")).

6.  Nel **raccolta DataGridColumnStyle** finestra di dialogo, aggiungere gli stili di colonna per lo stile di tabella è stato creato.

     Con il **raccolta DataGridColumnStyle**, è possibile aggiungere e rimuovere gli stili di colonna, impostare le proprietà di visualizzazione e il layout e impostare il nome del mapping e le stringhe di formattazione per i dati di colonne.

    > [!NOTE]
    >  Per altre informazioni sulle stringhe di formattazione, vedere [formattazione di tipi](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)