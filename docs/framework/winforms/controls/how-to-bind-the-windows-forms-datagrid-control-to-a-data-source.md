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
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332573"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 I moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo è appositamente progettato per visualizzare le informazioni da un'origine dati. Si associa il controllo in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo). Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Per associare a livello di codice il controllo DataGrid  
  
1. Scrivere codice per riempire il set di dati.  
  
     Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.  
  
     Il codice esatto che è usare dipende in cui il set di dati stia ottenendo i dati. In genere se il set di dati viene popolato direttamente da un database, si chiama il `Fill` metodo di un adattatore di dati, come nell'esempio seguente, che consente di popolare un set di dati denominato `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Se il set di dati viene riempito da un servizio Web XML, si crea in genere un'istanza del servizio nel codice e quindi chiamarla uno dei relativi metodi per restituire un set di dati. Quindi unire il set di dati dal servizio Web XML in set di dati locale. Nell'esempio seguente viene illustrato come è possibile creare un'istanza di un servizio Web XML chiamato `CategoriesService`, chiamare relativi `GetCategories` metodo e merge denominato set di dati risultante in un set di dati locale `DsCategories1`:  
  
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
  
2. Chiamare il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> passandogli l'origine dati e un membro dati. Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.  
  
    > [!NOTE]
    >  Se si esegue il binding della griglia per la prima volta, è possibile impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà. Tuttavia, è possibile reimpostare le proprietà dopo che sono stati impostati. Pertanto, è consigliabile usare sempre la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo).  
  
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
  
     Se la tabella Customers è l'unica tabella nel set di dati, è in alternativa è stato possibile associare la griglia in questo modo:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Facoltativo) Aggiungere gli stili tabella appropriata e gli stili di colonna nella griglia. Se non sono presenti stili di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo DataGrid](datagrid-control-overview-windows-forms.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Data binding di Windows Form](../windows-forms-data-binding.md)
