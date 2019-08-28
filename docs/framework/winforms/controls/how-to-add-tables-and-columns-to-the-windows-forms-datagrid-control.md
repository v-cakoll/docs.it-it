---
title: 'Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms'
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
ms.openlocfilehash: bfb0296566fecc2029df16d91c9c04d7daa4b4b5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046161"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

È possibile visualizzare i dati nel controllo <xref:System.Windows.Forms.DataGrid> Windows Forms in tabelle e colonne creando oggetti **DataGridTableStyle** e aggiungendoli all'oggetto **GridTableStylesCollection** , a cui è possibile accedere tramite il <xref:System.Windows.Forms.DataGrid> controllo Proprietà **TableStyles** . In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella proprietà **MappingName** dell'oggetto **DataGridTableStyle** . Per impostazione predefinita, uno stile di tabella senza stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne presenti nella tabella aggiungendo oggetti **DataGridColumnStyle** all'oggetto **GridColumnStylesCollection** , a cui si accede tramite la proprietà **GridColumnStyles** di ogni **DataGridTableStyle** oggetto.

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Per aggiungere una tabella e una colonna a una griglia a livello di codice

1. Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid Windows Forms a un'origine](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)dati.

    > [!CAUTION]
    > Quando si specificano gli stili delle colonne a livello di codice, creare sempre oggetti DataGridColumnStyle e aggiungerli all'oggetto **GridColumnStylesCollection** prima di aggiungere oggetti **DataGridTableStyle** al  **Oggetto GridTableStylesCollection** . Quando si aggiunge un oggetto **DataGridTableStyle** vuoto alla raccolta, gli oggetti DataGridColumnStyle vengono generati automaticamente. Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi oggetti DataGridColumnStyle con valori di MappingName duplicati all'oggetto **GridColumnStylesCollection** .

2. Dichiarare un nuovo stile di tabella e impostarne il nome del mapping.

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

3. Dichiarare un nuovo stile di colonna e impostarne il nome del mapping e altre proprietà.

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

4. Chiamare il metodo **Add** dell'oggetto **GridColumnStylesCollection** per aggiungere la colonna allo stile della tabella

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. Chiamare il metodo **Add** dell'oggetto **GridTableStylesCollection** per aggiungere lo stile della tabella alla griglia dei dati.

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

- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
