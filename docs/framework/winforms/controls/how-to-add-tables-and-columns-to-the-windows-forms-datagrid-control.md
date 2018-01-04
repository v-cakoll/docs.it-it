---
title: 'Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca34b5daff07b733ccf2bfb4269c11cff80c7549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile visualizzare i dati in Windows Form <xref:System.Windows.Forms.DataGrid> controllo in tabelle e colonne creando **DataGridTableStyle** oggetti e aggiungendoli al **GridColumnStylesCollection** oggetto, ovvero si accede tramite il <xref:System.Windows.Forms.DataGrid> del controllo **TableStyles** proprietà. Ogni stile tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella **DataGridTableStyle** dell'oggetto **MappingName** proprietà. Per impostazione predefinita, uno stile di tabella con nessuno stile di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne della tabella vengono visualizzati aggiungendo **DataGridColumnStyle** oggetti per il **GridColumnStylesCollection** oggetto, che è possibile accedere mediante il  **GridColumnStyles** proprietà di ogni **DataGridTableStyle** oggetto.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Per aggiungere una tabella e una colonna a una griglia dati a livello di codice  
  
1.  Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per ulteriori informazioni, vedere [procedura: associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Quando si specifica a livello di codice gli stili di colonna, creare sempre **DataGridColumnStyle** degli oggetti e aggiungerli al **GridColumnStylesCollection** oggetto prima di aggiungere  **DataGridTableStyle** oggetti per il **GridColumnStylesCollection** oggetto. Quando si aggiunge un oggetto vuoto **DataGridTableStyle** oggetto alla raccolta, **DataGridColumnStyle** gli oggetti vengono generati automaticamente. Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi **DataGridColumnStyle** oggetti con duplicato **MappingName** i valori per il **GridColumnStylesCollection**oggetto.  
  
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
  
3.  Dichiarare un nuovo stile di colonna e impostare altre proprietà e il nome di associazione.  
  
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
  
4.  Chiamare il **Aggiungi** metodo il **GridColumnStylesCollection** oggetto per aggiungere la colonna allo stile di tabella  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Chiamare il **Aggiungi** metodo il **GridColumnStylesCollection** oggetto da aggiungere lo stile di tabella alla griglia dei dati.  
  
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
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
