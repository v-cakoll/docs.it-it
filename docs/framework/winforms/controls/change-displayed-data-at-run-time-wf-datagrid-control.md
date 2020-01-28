---
title: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740599"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Dopo aver creato un Windows Forms <xref:System.Windows.Forms.DataGrid> utilizzando le funzionalità della fase di progettazione, è anche possibile modificare dinamicamente gli elementi dell'oggetto <xref:System.Data.DataSet> della griglia in fase di esecuzione. Possono essere incluse modifiche ai singoli valori della tabella o alla modifica dell'origine dati associata al controllo <xref:System.Windows.Forms.DataGrid>. Le modifiche ai singoli valori vengono eseguite tramite l'oggetto <xref:System.Data.DataSet> e non con il controllo <xref:System.Windows.Forms.DataGrid>.  
  
### <a name="to-change-data-programmatically"></a>Per modificare i dati a livello di programmazione  
  
1. Specificare la tabella desiderata dall'oggetto <xref:System.Data.DataSet> e la riga e il campo desiderati della tabella e impostare la cella su un valore uguale a quello nuovo.  
  
    > [!NOTE]
    > Per specificare la prima tabella del <xref:System.Data.DataSet> o la prima riga della tabella, utilizzare 0.  
  
     Nell'esempio seguente viene illustrato come modificare la seconda voce della prima riga della prima tabella di un set di dati facendo clic su `Button1`. Il <xref:System.Data.DataSet> (`ds`) e le tabelle (`0` e `1`) sono stati creati in precedenza.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     In fase di esecuzione è possibile usare il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> per associare il controllo <xref:System.Windows.Forms.DataGrid> a un'origine dati diversa. Ad esempio, è possibile disporre di diversi controlli dati ADO.NET, ciascuno connesso a un database diverso.  
  
### <a name="to-change-the-datasource-programmatically"></a>Per modificare l'origine dati a livello di codice  
  
1. Impostare il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> sul nome dell'origine dati e della tabella a cui si desidera eseguire l'associazione.  
  
     Nell'esempio seguente viene illustrato come modificare l'origine della data utilizzando il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> in un controllo dati ADO.NET (adoPubsAuthors) connesso alla tabella authors nel database pubs.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti DataSet ADO.NET](../../data/adonet/ado-net-datasets.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
