---
title: "Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati"
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
ms.openlocfilehash: bac24c2dd622ea780408e902d08708ac09561044
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922730"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il controllo <xref:System.Windows.Forms.DataGrid> Windows Forms è progettato in modo specifico per visualizzare le informazioni di un'origine dati. Il controllo viene associato in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo. Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Per associare i dati al controllo DataGrid a livello di codice  
  
1. Scrivere il codice per riempire il set di dati.  
  
     Se l'origine dati è un set di dati o una vista dati basata su una tabella del set di dati, aggiungere il codice al form per riempire il set di dati.  
  
     Il codice esatto utilizzato dipende dalla posizione in cui il set di dati recupera i dati. Se il set di dati viene popolato direttamente da un database, in genere `Fill` si chiama il metodo di un adattatore dati, come nell'esempio seguente, che popola un set `DsCategories1`di dati denominato:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Se il set di dati viene compilato da un servizio Web XML, in genere si crea un'istanza del servizio nel codice e quindi si chiama uno dei metodi per restituire un set di dati. È quindi possibile unire il set di dati dal servizio Web XML nel set di dati locale. Nell'esempio seguente viene illustrato come è possibile creare un'istanza di un servizio Web XML `CategoriesService`denominato, `GetCategories` chiamare il metodo e unire il set di dati risultante in un set `DsCategories1`di dati locale denominato:  
  
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
  
2. Chiamare il <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo del controllo, passandogli l'origine dati e un membro dati. Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.  
  
    > [!NOTE]
    > Se si associa la griglia per la prima volta, è possibile impostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> del controllo. Tuttavia, non è possibile reimpostare queste proprietà dopo che sono state impostate. È pertanto consigliabile utilizzare sempre il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo.  
  
     Nell'esempio seguente viene illustrato come è possibile eseguire l'associazione a livello di codice alla tabella Customers in un set di dati denominato `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Se la tabella Customers è l'unica tabella del set di dati, è possibile associare la griglia in questo modo:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. Opzionale Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia. Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con la formattazione minima e con tutte le colonne visibili.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sul controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Aggiungere tabelle e colonne al controllo Windows Forms DataGrid](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Data binding in Windows Form](../windows-forms-data-binding.md)
