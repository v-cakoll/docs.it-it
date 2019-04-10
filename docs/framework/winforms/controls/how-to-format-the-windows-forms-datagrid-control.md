---
title: 'Procedura: Formattare il controllo DataGrid di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 8e5c41d6f146e6abef8d7670e6191b587ac86c92
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336122"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Procedura: Formattare il controllo DataGrid di Windows Forms
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Applicazione di colori diversi alle varie parti di un <xref:System.Windows.Forms.DataGrid> il controllo è utile per rendere più semplice da leggere e interpretare le informazioni in esso. Colore può essere applicato alle righe e colonne. Le righe e colonne possono anche essere nascoste o visualizzate a discrezione dell'utente.  
  
 Esistono tre aspetti di base della formattazione di <xref:System.Windows.Forms.DataGrid> controllo. È possibile impostare proprietà per definire uno stile predefinito in cui vengono visualizzati dati. Da quella base, è quindi possibile personalizzare il modo che in fase di esecuzione vengono visualizzate determinate tabelle. Infine, è possibile modificare le colonne da visualizzare nella griglia dei dati, nonché i colori e altro di formattazione che viene visualizzato.  
  
 Come passaggio iniziale in una griglia dei dati di formattazione, è possibile impostare le proprietà del <xref:System.Windows.Forms.DataGrid> stesso. Queste scelte di colori e il formato formano una base da cui è quindi possibile apportare modifiche a seconda delle tabelle di dati e le colonne visualizzate.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid  
  
1. Impostare le proprietà seguenti come appropriato:  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Il <xref:System.Windows.Forms.DataGrid.BackColor%2A> proprietà definisce il colore delle righe pari della griglia. Quando si imposta il <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà su un colore diverso, tutte le altre righe è impostata su questo nuovo colore (righe 1, 3, 5 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Il colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre il <xref:System.Windows.Forms.DataGrid.BackColor%2A> e <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà determina il colore delle righe nella griglia di <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> proprietà determina il colore dell'area non occupata, che è visibile solo quando la griglia è necessario scorrere verso il basso, o se solo alcune righe contenute nel la griglia.|  
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Il colore di primo piano delle intestazioni di colonna della griglia, compresi il testo dell'intestazione di colonna e le icone più/meno (da espande le righe quando vengono visualizzate più tabelle correlate).|  
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
    >  Tenere presente, quando si personalizzano i colori dei controlli, che è possibile rendere il controllo inaccessibile, a causa di scarsa colore scelto (ad esempio, rosso e verde). Utilizzare i colori disponibili nel **colori di sistema** tavolozza per evitare questo problema.  
  
     Le procedure seguenti presuppongono il form contenga un <xref:System.Windows.Forms.DataGrid> controllo associato a una tabella di dati. Per altre informazioni, vedere [il controllo DataGrid di Windows Form di associazione a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Per impostare lo stile di tabella e colonna di una tabella di dati a livello di codice  
  
1. Creare un nuovo stile di tabella e impostare le relative proprietà.  
  
2. Creare uno stile colonna e impostare le relative proprietà.  
  
3. Aggiungere lo stile della colonna alla raccolta di stili colonna stili di tabella.  
  
4. Aggiungere lo stile della tabella alla raccolta di stili di tabella della griglia dei dati.  
  
5. Nell'esempio seguente, creare un'istanza di una nuova <xref:System.Windows.Forms.DataGridTableStyle> e impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà.  
  
6. Creare una nuova istanza di un **GridColumnStyle** e impostare relativo **MappingName** (e alcune altre proprietà di layout e la visualizzazione).  
  
7. Ripetere i passaggi da 2 a 6 per ogni stile di colonna che si desidera creare.  
  
     Nell'esempio seguente viene illustrato come un <xref:System.Windows.Forms.DataGridTextBoxColumn> viene creato, poiché un nome da visualizzare nella colonna. È inoltre necessario aggiungere lo stile della colonna per il <xref:System.Windows.Forms.GridColumnStylesCollection> dello stile di tabella, e si aggiunge lo stile di tabella per il <xref:System.Windows.Forms.GridTableStylesCollection> la griglia dei dati.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
