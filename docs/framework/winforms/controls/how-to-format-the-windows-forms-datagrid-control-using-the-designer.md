---
title: 'Procedura: formattare il controllo DataGrid Windows Form mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c9c82044e7136f05d64a20fb24ee0b209742caf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: formattare il controllo DataGrid Windows Form mediante la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 L'applicazione di colori diversi alle varie parti di un <xref:System.Windows.Forms.DataGrid> il controllo è utile per rendere più semplice leggere e interpretare le informazioni in essa contenuti. Colore può essere applicato in righe e colonne. Righe e colonne possono inoltre essere nascoste o visualizzate a propria discrezione.  
  
 Esistono tre aspetti di base di formattazione di <xref:System.Windows.Forms.DataGrid> controllo:  
  
-   È possibile impostare proprietà per definire uno stile predefinito in cui vengono visualizzati dati.  
  
-   Da tale base, è quindi possibile personalizzare il modo in cui che vengono visualizzate determinate tabelle in fase di esecuzione.  
  
-   Infine, è possibile modificare le colonne da visualizzare nella griglia dei dati, nonché i colori e altro formattazione che viene visualizzato.  
  
 Come passaggio iniziale per la formattazione di una griglia dati, è possibile impostare le proprietà del <xref:System.Windows.Forms.DataGrid> stesso. Queste scelte di colore e il formato formano una base da cui è quindi possibile apportare modifiche a seconda delle tabelle di dati e le colonne visualizzate.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> controllo non sarà il **della casella degli strumenti** per impostazione predefinita. Per ulteriori informazioni, vedere [procedura: aggiungere elementi alla casella degli strumenti](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.DataGrid>.  
  
2.  Nel **proprietà** finestra, impostare le proprietà seguenti, come appropriato.  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Il `BackColor` proprietà definisce il colore delle righe pari della griglia. Quando si imposta la <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> su un colore diverso, ogni riga è impostata su questo nuovo colore (righe 1, 3, 5 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre il <xref:System.Windows.Forms.DataGrid.BackColor%2A> e <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà determina il colore delle righe nella griglia, il <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> proprietà determina il colore dell'area all'esterno dell'area riga, che è visibile solo quando si scorre la griglia verso il basso, o se solo alcune righe sono Nella griglia è contenuto.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Stile del bordo della griglia, uno del <xref:System.Windows.Forms.BorderStyle> valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Il colore di sfondo del titolo della finestra della griglia visualizzata immediatamente sopra la griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Il tipo di carattere della didascalia nella parte superiore della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Il colore di sfondo del titolo della finestra della griglia.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Il tipo di carattere utilizzato per visualizzare il testo nella griglia.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Il colore del tipo di carattere visualizzato per i dati nelle righe della griglia di dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Il colore delle linee della griglia della griglia di dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Lo stile delle linee che separano le celle della griglia, uno del <xref:System.Windows.Forms.DataGridLineStyle> valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Il colore di sfondo delle intestazioni di riga e colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Il tipo di carattere utilizzato per le intestazioni di colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Vengono visualizzati il colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione di colonna e il segno più (+) e segno meno (-) glifi che espandere e comprimere le righe quando più tabelle correlate.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Il colore del testo di tutti i collegamenti nella griglia dei dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In una tabella figlio, questo è il colore di sfondo delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In una tabella figlio, questo è il colore di primo piano delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina se i nomi di tabella e di colonna vengono visualizzati nella riga padre, tramite il <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Larghezza predefinita (in pixel) delle colonne della griglia. Impostare questa proprietà prima di reimpostare il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà (sia separatamente, o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo), o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Altezza della riga, in pixel, di righe nella griglia. Impostare questa proprietà prima di reimpostare il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà (sia separatamente, o tramite il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo), o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|La larghezza delle intestazioni di riga della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Quando una riga o cella è selezionata, questo è il colore di sfondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Quando una riga o cella è selezionata, questo è il colore primo piano.|  
  
    > [!NOTE]
    >  Quando si desidera personalizzare i colori dei controlli, è possibile rendere il controllo inaccessibile a causa delle scelte di colori (ad esempio, rosso e verde). Utilizzare i colori disponibili nel **colori di sistema** tavolozza per evitare questo problema.  
  
     La procedura seguente richiede un <xref:System.Windows.Forms.DataGrid> controllo associato a una tabella di dati. Per ulteriori informazioni, vedere [procedura: associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Per impostare lo stile di tabella e colonna di una tabella di dati in fase di progettazione  
  
1.  Selezionare il <xref:System.Windows.Forms.DataGrid> controllo sul form.  
  
2.  Nel **proprietà** finestra, seleziona il <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà e fare clic su di **i puntini di sospensione** (![schermata VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) pulsante.  
  
3.  Nel **raccolta DataGridTableStyle** la finestra di dialogo, fare clic su **Aggiungi** per aggiungere uno stile tabella alla raccolta.  
  
     Con il **raccolta DataGridTableStyle**, è possibile aggiungere e rimuovere stili di tabella, impostare la visualizzazione e proprietà di layout e impostare il nome di mapping per gli stili di tabella.  
  
4.  Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà sul nome di mapping per ogni stile tabella.  
  
     Il nome di mapping viene utilizzato per specificare lo stile di tabella deve essere utilizzato con la tabella.  
  
5.  Nel **raccolta DataGridTableStyle**, selezionare il <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà e fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton ")).  
  
6.  Nel **raccolta DataGridColumnStyle** finestra di dialogo, aggiungere gli stili di colonna per lo stile di tabella è stato creato.  
  
     Con il **raccolta DataGridColumnStyle**, è possibile aggiungere e rimuovere gli stili di colonna, impostare le proprietà di visualizzazione e il layout e impostare il nome di mapping e le stringhe di formattazione per i dati di colonne.  
  
    > [!NOTE]
    >  Per ulteriori informazioni sulla formattazione di stringhe, vedere [formattazione dei tipi di](../../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
