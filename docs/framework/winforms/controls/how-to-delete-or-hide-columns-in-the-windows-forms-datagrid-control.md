---
title: 'Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form'
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
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65257ec5f9ca51a795abca119e5449d6219042bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Puoi eliminare o nascondere le colonne in Windows Form a livello di programmazione <xref:System.Windows.Forms.DataGrid> controllo utilizzando le proprietà e metodi del <xref:System.Windows.Forms.GridColumnStylesCollection> e <xref:System.Windows.Forms.DataGridColumnStyle> oggetti (che sono membri del <xref:System.Windows.Forms.DataGridTableStyle> classe).  
  
 Le colonne eliminate o nascoste ancora presenti nell'origine dei dati, la griglia è associata a e può comunque accedere a livello di codice. Non sono semplicemente più visibile nel controllo datagrid.  
  
> [!NOTE]
>  Se l'applicazione non accedere ad alcune colonne di dati e non si desidera visualizzarli nel controllo datagrid, quindi è probabile che non necessario includerli in primo luogo nell'origine dati.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Per eliminare una colonna da DataGrid a livello di codice  
  
1.  Nella sezione delle dichiarazioni del form, dichiarare una nuova istanza di <xref:System.Windows.Forms.DataGridTableStyle> classe.  
  
2.  Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> proprietà alla tabella nell'origine dati che si desidera applicare lo stile. L'esempio seguente usa il <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, si presuppone che è già impostato.  
  
3.  Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella della griglia.  
  
4.  Chiamare il <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> metodo il <xref:System.Windows.Forms.DataGrid>del <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> insieme, specificando l'indice della colonna da eliminare.  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Per nascondere una colonna nel controllo DataGrid a livello di codice  
  
1.  Nella sezione delle dichiarazioni del form, dichiarare una nuova istanza di <xref:System.Windows.Forms.DataGridTableStyle> classe.  
  
2.  Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà del <xref:System.Windows.Forms.DataGridTableStyle> alla tabella nell'origine dati che si desidera applicare lo stile. Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, si presuppone che è già impostato.  
  
3.  Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella della griglia.  
  
4.  Nascondere la colonna impostando il relativo `Width` proprietà su 0, che specifica l'indice di colonna della colonna da nascondere.  
  
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
 [Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
