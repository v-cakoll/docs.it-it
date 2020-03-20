---
title: Modifica dei dati visualizzati in fase di esecuzione nel controllo DataGridChange Displayed Data at Run Time in DataGrid Control
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142381"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Dopo aver creato un <xref:System.Windows.Forms.DataGrid> Windows Form utilizzando le funzionalità della fase di <xref:System.Data.DataSet> progettazione, è anche possibile modificare dinamicamente gli elementi dell'oggetto della griglia in fase di esecuzione. Ciò può includere modifiche ai singoli valori della tabella <xref:System.Windows.Forms.DataGrid> o la modifica dell'origine dati associata al controllo. Le modifiche ai singoli <xref:System.Data.DataSet> valori vengono <xref:System.Windows.Forms.DataGrid> eseguite tramite l'oggetto, non il controllo.  
  
### <a name="to-change-data-programmatically"></a>Per modificare i dati a livello di codiceTo change data programmatically  
  
1. Specificare la tabella <xref:System.Data.DataSet> desiderata dall'oggetto e la riga e il campo desiderati dalla tabella e impostare la cella uguale al nuovo valore.  
  
    > [!NOTE]
    > Per specificare la <xref:System.Data.DataSet> prima tabella della o della prima riga della tabella, utilizzare 0.  
  
     Nell'esempio seguente viene illustrato come modificare la seconda voce della prima `Button1`riga della prima tabella di un dataset facendo clic su . I <xref:System.Data.DataSet> `ds`campi (`0` ) `1`e le tabelle ( e ) sono stati creati in precedenza.  
  
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
  
     (Visual C, Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     In fase di esecuzione <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> è possibile <xref:System.Windows.Forms.DataGrid> utilizzare il metodo per associare il controllo a un'origine dati diversa. Ad esempio, è possibile disporre di diversi controlli dati ADO.NET, ognuno connesso a un database diverso.  
  
### <a name="to-change-the-datasource-programmatically"></a>Per modificare DataSource a livello di codiceTo change the DataSource programmatically  
  
1. Impostare <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> il metodo sul nome dell'origine dati e della tabella a cui si desidera eseguire l'associazione.  
  
     Nell'esempio seguente viene illustrato come <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> modificare l'origine della data utilizzando il metodo per un controllo dati ADO.NET (adoPubsAuthors) connesso alla tabella Authors del database Pubs.  
  
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
- [Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Procedura: associare il controllo DataGrid Windows Form a un'origine dati](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
