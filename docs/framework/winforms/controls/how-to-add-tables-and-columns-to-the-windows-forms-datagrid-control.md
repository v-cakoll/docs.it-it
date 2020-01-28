---
title: Aggiungere tabelle e colonne al controllo DataGrid
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
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747216"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

È possibile visualizzare i dati nel controllo <xref:System.Windows.Forms.DataGrid> Windows Forms nelle tabelle e nelle colonne creando oggetti **DataGridTableStyle** e aggiungendoli all'oggetto **GridTableStylesCollection** , a cui si accede tramite la proprietà **TableStyles** del controllo <xref:System.Windows.Forms.DataGrid>. In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella proprietà **MappingName** dell'oggetto **DataGridTableStyle** . Per impostazione predefinita, uno stile di tabella senza stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne presenti nella tabella aggiungendo oggetti **DataGridColumnStyle** all'oggetto **GridColumnStylesCollection** , a cui si accede tramite la proprietà **GridColumnStyles** di ogni oggetto **DataGridTableStyle** .

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Per aggiungere una tabella e una colonna a una griglia a livello di codice

1. Per visualizzare i dati nella tabella, è necessario innanzitutto associare il controllo <xref:System.Windows.Forms.DataGrid> a un set di dati. Per altre informazioni, vedere [procedura: associare il controllo DataGrid Windows Forms a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

    > [!CAUTION]
    > Quando si specificano gli stili delle colonne a livello di codice, creare sempre oggetti **DataGridColumnStyle** e aggiungerli all'oggetto **GridColumnStylesCollection** prima di aggiungere oggetti **DataGridTableStyle** all'oggetto **GridTableStylesCollection** . Quando si aggiunge un oggetto **DataGridTableStyle** vuoto alla raccolta, gli oggetti **DataGridColumnStyle** vengono generati automaticamente. Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi oggetti **DataGridColumnStyle** con valori di **MappingName** duplicati all'oggetto **GridColumnStylesCollection** .

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
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
