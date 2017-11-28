---
title: 'Procedura: associare il controllo DataGrid Windows Form a un''origine dati'
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
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 185c094b32f0de7a1a26da144601961d92a625b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Procedura: associare il controllo DataGrid Windows Form a un'origine dati
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Form <xref:System.Windows.Forms.DataGrid> controllo è progettato specificamente per visualizzare le informazioni da un'origine dati. Associare il controllo in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo. Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Per associare a livello di codice il controllo DataGrid  
  
1.  Scrivere codice per riempire il set di dati.  
  
     Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.  
  
     Il codice esatto che è utilizzare dipende in cui il set di dati Ottiene i dati. Se il set di dati viene popolato direttamente da un database, si chiama in genere il `Fill` metodo di un adattatore di dati, come nell'esempio seguente, che popola un set di dati denominato `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Se il set di dati viene riempito da un servizio Web XML, in genere creare un'istanza del servizio nel codice e quindi chiamare uno dei relativi metodi per restituire un set di dati. Quindi di unire il set di dati dal servizio Web XML in set di dati locale. Nell'esempio seguente viene illustrato come è possibile creare un'istanza di un servizio Web XML denominato `CategoriesService`, chiamare il relativo `GetCategories` (metodo) e merge, il set di dati risultante in un set di dati locale denominato `DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  Chiamare il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo), passando l'origine dati e un membro dati. Se è necessario passare in modo esplicito un membro dati, passare una stringa vuota.  
  
    > [!NOTE]
    >  Se si desidera associare la griglia per la prima volta, è possibile impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà. Tuttavia, non è possibile reimpostare le proprietà dopo che sono stati impostati. Pertanto, è consigliabile utilizzare sempre il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo.  
  
     Nell'esempio seguente viene illustrato come è possibile associare a livello di codice alla tabella Customers in un set di dati denominato `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Se la tabella Customers è l'unica tabella nel set di dati, è in alternativa possibile associare la griglia in questo modo:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (Facoltativo) Aggiungere gli stili tabella appropriata e gli stili di colonna nella griglia. Se sono presenti nessuno stile di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Data binding in Windows Form](../../../../docs/framework/winforms/windows-forms-data-binding.md)
