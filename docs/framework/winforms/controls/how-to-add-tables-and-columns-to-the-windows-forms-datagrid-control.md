---
title: 'Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: be0bb6d3d7b8d8b362653257139e83900dbb2780
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717870"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile visualizzare i dati nei moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo in tabelle e colonne creando **DataGridTableStyle** oggetti e ad aggiungerle nel **GridTableStylesCollection** oggetto, ovvero si accede tramite il <xref:System.Windows.Forms.DataGrid> del controllo **TableStyles** proprietà. Ogni stile tabella viene visualizzato il contenuto di qualsiasi tabella dati specificata nel **DataGridTableStyle** dell'oggetto **MappingName** proprietà. Per impostazione predefinita, uno stile di tabella con senza stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne della tabella vengono visualizzati aggiungendo **DataGridColumnStyle** gli oggetti per il **GridColumnStylesCollection** oggetto, che è possibile accedere mediante il  **GridColumnStyles** proprietà della ognuno **DataGridTableStyle** oggetto.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Per aggiungere una tabella e una colonna a un DataGrid a livello di codice  
  
1.  Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Quando si specifica a livello di programmazione gli stili di colonna, creare sempre **DataGridColumnStyle** degli oggetti e aggiungerli al **GridColumnStylesCollection** oggetto prima di aggiungere  **DataGridTableStyle** gli oggetti per il **GridTableStylesCollection** oggetto. Quando si aggiunge un oggetto vuoto **DataGridTableStyle** oggetto nella raccolta **DataGridColumnStyle** gli oggetti vengono generati automaticamente per l'utente. Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi **DataGridColumnStyle** gli oggetti con duplicato **MappingName** valori il **GridColumnStylesCollection**oggetto.  
  
2.  Dichiarare un nuovo stile di tabella e impostarne il nome di mapping.  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  Dichiarare un nuovo stile di colonna e impostare il nome di associazione e altre proprietà.  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  Chiamare il **Add** metodo per il **GridColumnStylesCollection** oggetto a cui aggiungere la colonna per lo stile di tabella  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Chiamare il **Add** metodo per il **GridTableStylesCollection** oggetto a cui aggiungere lo stile di tabella per la griglia dei dati.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
