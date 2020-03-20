---
title: Format DataGrid (controllo)
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
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182141"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Procedura: formattare il controllo DataGrid di Windows Form
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 L'applicazione di colori diversi <xref:System.Windows.Forms.DataGrid> a varie parti di un controllo può contribuire a semplificare la lettura e l'interpretazione delle informazioni in esso contenute. Il colore può essere applicato a righe e colonne. Righe e colonne possono anche essere nascoste o visualizzate a propria discrezione.  
  
 Esistono tre aspetti di base <xref:System.Windows.Forms.DataGrid> della formattazione del controllo. È possibile impostare le proprietà per stabilire uno stile di default in cui vengono visualizzati i dati. Da tale base, è quindi possibile personalizzare la modalità di visualizzazione di determinate tabelle in fase di esecuzione. Infine, è possibile modificare le colonne visualizzate nella griglia dei dati, nonché i colori e altre formattazioni visualizzate.  
  
 Come passaggio iniziale nella formattazione di una <xref:System.Windows.Forms.DataGrid> griglia di dati, è possibile impostare le proprietà della stessa. Queste scelte di colore e formato costituiscono una base da cui è quindi possibile apportare modifiche a seconda delle tabelle dati e delle colonne visualizzate.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Per stabilire uno stile predefinito per il controllo DataGrid  
  
1. Impostare le seguenti proprietà in base alle esigenze:  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La <xref:System.Windows.Forms.DataGrid.BackColor%2A> proprietà definisce il colore delle righe pari della griglia. Quando si <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> imposta la proprietà su un colore diverso, ogni altra riga viene impostata su questo nuovo colore (righe 1, 3, 5 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Colore di sfondo delle righe pari della griglia (righe 0, 2, 4, 6 e così via).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mentre <xref:System.Windows.Forms.DataGrid.BackColor%2A> le <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> proprietà e determinano il colore <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> delle righe nella griglia, la proprietà determina il colore dell'area non riga, visibile solo quando si scorre la griglia verso il basso o se nella griglia sono contenute solo poche righe.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Stile del bordo della griglia, <xref:System.Windows.Forms.BorderStyle> uno dei valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Colore di sfondo della didascalia della finestra della griglia che appare immediatamente sopra la griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Tipo di carattere della didascalia nella parte superiore della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Colore di sfondo della didascalia della finestra della griglia.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Tipo di carattere utilizzato per visualizzare il testo nella griglia.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Colore del tipo di carattere visualizzato dai dati nelle righe della griglia dei dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Colore delle linee della griglia della griglia di dati.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Stile delle linee che separano le celle della <xref:System.Windows.Forms.DataGridLineStyle> griglia, uno dei valori di enumerazione.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Colore di sfondo delle intestazioni di riga e di colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Tipo di carattere utilizzato per le intestazioni di colonna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Colore di primo piano delle intestazioni di colonna della griglia, inclusi il testo dell'intestazione di colonna e i glifi più/meno (per espandere le righe quando vengono visualizzate più tabelle correlate).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Colore del testo di tutti i collegamenti nella griglia dei dati, inclusi i collegamenti alle tabelle figlio, il nome della relazione e così via.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|In una tabella figlio, questo è il colore di sfondo delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|In una tabella figlio, questo è il colore di primo piano delle righe padre.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina se i nomi di tabella e colonna vengono visualizzati nella riga padre, tramite l'enumerazione <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> .|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Larghezza predefinita (in pixel) delle colonne della griglia. Impostare questa proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> prima <xref:System.Windows.Forms.DataGrid.DataMember%2A> di reimpostare le <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> proprietà e (separatamente o tramite il metodo ) o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Altezza delle righe (in pixel) delle righe nella griglia. Impostare questa proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> prima <xref:System.Windows.Forms.DataGrid.DataMember%2A> di reimpostare le <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> proprietà e (separatamente o tramite il metodo ) o la proprietà non avrà alcun effetto.<br /><br /> La proprietà non può essere impostata su un valore minore di 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Larghezza delle intestazioni di riga della griglia.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Quando si seleziona una riga o una cella, questo è il colore di sfondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Quando si seleziona una riga o una cella, questo è il colore di primo piano.|  
  
    > [!NOTE]
    > Tenere presente che quando si personalizzano i colori dei controlli è possibile rendere il controllo inaccessibile, a causa della scarsa scelta del colore (ad esempio, rosso e verde). Utilizzare i colori disponibili nella tavolozza **Colori** di sistema per evitare questo problema.  
  
     Nelle procedure seguenti si <xref:System.Windows.Forms.DataGrid> presuppone che il form disponga di un controllo associato a una tabella dati. Per ulteriori informazioni, vedere [Associazione del controllo DataGrid Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Per impostare lo stile di tabella e colonna di una tabella dati a livello di codiceTo set the table and column style of a data table programmatically  
  
1. Creare un nuovo stile di tabella e impostarne le proprietà.  
  
2. Creare uno stile di colonna e impostarne le proprietà.  
  
3. Aggiungere lo stile di colonna alla raccolta di stili di colonna dello stile di tabella.  
  
4. Aggiungere lo stile di tabella all'insieme di stili di tabella della griglia dei dati.  
  
5. Nell'esempio seguente, creare un'istanza di un nuovo <xref:System.Windows.Forms.DataGridTableStyle> e impostarne la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà.  
  
6. Creare una nuova istanza di un **GridColumnStyle** e impostarne **il MappingName** (e alcune altre proprietà di layout e visualizzazione).  
  
7. Ripetere i passaggi da 2 a 6 per ogni stile di colonna che si desidera creare.  
  
     Nell'esempio seguente viene <xref:System.Windows.Forms.DataGridTextBoxColumn> illustrato come viene creato un oggetto, perché un nome deve essere visualizzato nella colonna. Inoltre, aggiungere lo stile di <xref:System.Windows.Forms.GridColumnStylesCollection> colonna per lo stile di tabella <xref:System.Windows.Forms.GridTableStylesCollection> e aggiungere lo stile di tabella per la griglia dei dati.  
  
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
- [Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
