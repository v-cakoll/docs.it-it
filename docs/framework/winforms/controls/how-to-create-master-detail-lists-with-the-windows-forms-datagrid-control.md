---
title: 'Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 6ff13264709c4557d698435ac05b7759be58f1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712892"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Se il <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile utilizzare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato master/dettaglio. Uno <xref:System.Windows.Forms.DataGrid> designato come la griglia principale, e il secondo può essere tuttavia designato nella griglia dei dettagli. Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlati vengono visualizzate nell'elenco di dettagli. Ad esempio, se il <xref:System.Data.DataSet> contiene una tabella Customers e una tabella di ordini correlata, si specificherà la tabella Customers a griglia principale e la tabella Orders alla griglia dei dettagli. Quando un cliente viene selezionato nella griglia principale, tutti gli ordini associati a tale cliente nella tabella Orders verrebbero visualizzati nella griglia dettagli.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Per impostare una relazione master/dettagli a livello di codice  
  
1.  Creare due nuovi <xref:System.Windows.Forms.DataGrid> consente di controllare e impostare le relative proprietà.  
  
2.  Aggiungere tabelle al set di dati.  
  
3.  Dichiarare una variabile di tipo <xref:System.Data.DataRelation> per rappresentare la relazione da creare.  
  
4.  Creare un'istanza della relazione specificando un nome per la relazione e la tabella, colonna e articoli che limiteranno le due tabelle.  
  
5.  Aggiungere la relazione con il <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Relations%2A> raccolta.  
  
6.  Usare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo del <xref:System.Windows.Forms.DataGrid> ognuna delle griglie per associare il <xref:System.Data.DataSet>.  
  
     Nell'esempio seguente viene illustrato come impostare una relazione master/dettaglio tra le tabelle Customers e Orders in un oggetto generato in precedenza <xref:System.Data.DataSet> (`ds`).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Cenni preliminari sul controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
