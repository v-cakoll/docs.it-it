---
title: Eliminare o nascondere colonne nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743291"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile eliminare o nascondere a livello di codice le colonne nel controllo Windows Forms <xref:System.Windows.Forms.DataGrid> usando le proprietà e i metodi degli oggetti <xref:System.Windows.Forms.GridColumnStylesCollection> e <xref:System.Windows.Forms.DataGridColumnStyle> (membri della classe <xref:System.Windows.Forms.DataGridTableStyle>).  
  
 Le colonne eliminate o nascoste sono ancora presenti nell'origine dati a cui è associata la griglia ed è comunque possibile accedervi a livello di codice. Non sono più visibili nell'elemento DataGrid.  
  
> [!NOTE]
> Se l'applicazione non accede ad alcune colonne di dati e non si desidera che vengano visualizzate nel DataGrid, è probabile che non sia necessario includerle nell'origine dati.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Per eliminare una colonna da DataGrid a livello di codice  
  
1. Nell'area dichiarazioni del modulo dichiarare una nuova istanza della classe <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> sulla tabella nell'origine dati a cui si desidera applicare lo stile. Nell'esempio seguente viene utilizzata la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, che presuppone che sia già impostata.  
  
3. Aggiungere il nuovo oggetto <xref:System.Windows.Forms.DataGridTableStyle> alla raccolta di stili di tabella del DataGrid.  
  
4. Chiamare il metodo <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> della raccolta di <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> del <xref:System.Windows.Forms.DataGrid>, specificando l'indice di colonna della colonna da eliminare.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Per nascondere una colonna nella griglia a livello di codice  
  
1. Nell'area dichiarazioni del modulo dichiarare una nuova istanza della classe <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> della <xref:System.Windows.Forms.DataGridTableStyle> alla tabella nell'origine dati a cui si desidera applicare lo stile. Nell'esempio di codice seguente viene usata la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, che presuppone che sia già impostata.  
  
3. Aggiungere il nuovo oggetto <xref:System.Windows.Forms.DataGridTableStyle> alla raccolta di stili di tabella del DataGrid.  
  
4. Nascondere la colonna impostando la relativa proprietà `Width` su 0, specificando l'indice della colonna da nascondere.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
