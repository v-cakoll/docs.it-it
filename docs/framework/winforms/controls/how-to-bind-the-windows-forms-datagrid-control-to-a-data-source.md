---
title: Associare un controllo DataGrid a un'origine datiBind DataGrid Control to a Data Source
ms.date: 03/30/2017
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
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182251"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Procedura: associare il controllo DataGrid Windows Form a un'origine dati
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il controllo <xref:System.Windows.Forms.DataGrid> Windows Form è progettato in modo specifico per visualizzare informazioni da un'origine dati. Associare il controllo in fase <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> di esecuzione chiamando il metodo . Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Per associare dati al controllo DataGrid a livello di codiceTo data-bind the DataGrid control programmatically  
  
1. Scrivere il codice per riempire il set di dati.  
  
     Se l'origine dati è un set di dati o una visualizzazione dati basata su una tabella del set di dati, aggiungere codice al form per riempire il set di dati.  
  
     Il codice esatto utilizzato dipende da dove il dataset sta ottenendo i dati. Se il dataset viene popolato direttamente da `Fill` un database, in genere si chiama il metodo di `DsCategories1`un adattatore dati, come nell'esempio seguente, che popola un set di dati denominato :  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Se il set di dati viene compilato da un servizio Web XML, in genere si crea un'istanza del servizio nel codice e quindi si chiama uno dei relativi metodi per restituire un set di dati. È quindi possibile unire il set di dati dal servizio Web XML al dataset locale. Nell'esempio riportato di seguito viene illustrato come `CategoriesService`creare `GetCategories` un'istanza di un servizio Web `DsCategories1`XML denominato , chiamare il relativo metodo e unire il dataset risultante in un dataset locale denominato :  
  
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
  
2. Chiamare <xref:System.Windows.Forms.DataGrid> il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del controllo, passandogli l'origine dati e un membro dati. Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.  
  
    > [!NOTE]
    > Se si associa la griglia per la prima volta, <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> è possibile impostare le proprietà e del controllo. Tuttavia, non è possibile reimpostare queste proprietà una volta impostate. Pertanto, si consiglia di <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> utilizzare sempre il metodo .  
  
     Nell'esempio seguente viene illustrato come eseguire l'associazione `DsCustomers1`a livello di codice alla tabella Customers in un set di dati denominato :  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Se la tabella Customers è l'unica tabella del set di dati, in alternativa è possibile associare la griglia in questo modo:If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Facoltativo) Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia. Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con una formattazione minima e con tutte le colonne visibili.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Data binding di Windows Form](../windows-forms-data-binding.md)
