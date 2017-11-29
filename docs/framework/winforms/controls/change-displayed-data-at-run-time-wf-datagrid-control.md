---
title: 'Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form'
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
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45772035a7f2229ca0e0320ee9b65eb128c4fc32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Dopo aver creato un Windows Form <xref:System.Windows.Forms.DataGrid> utilizzando le funzionalità in fase di progettazione, è inoltre possibile modificare dinamicamente gli elementi del <xref:System.Data.DataSet> oggetto della griglia in fase di esecuzione. Ciò può includere le modifiche dei singoli valori della tabella o dell'origine dati a cui è associata la <xref:System.Windows.Forms.DataGrid> controllo. Vengono apportate modifiche ai singoli valori tramite la <xref:System.Data.DataSet> oggetto, non il <xref:System.Windows.Forms.DataGrid> controllo.  
  
### <a name="to-change-data-programmatically"></a>Per modificare i dati a livello di codice  
  
1.  Specificare la tabella desiderata di <xref:System.Data.DataSet> oggetto e riga e campo della tabella e impostare la cella per il nuovo valore desiderato.  
  
    > [!NOTE]
    >  Per specificare la prima tabella della <xref:System.Data.DataSet> o la prima riga della tabella, usare 0.  
  
     Nell'esempio seguente viene illustrato come modificare la seconda voce della prima riga della prima tabella di un set di dati, fare clic su `Button1`. Il <xref:System.Data.DataSet> (`ds`) e le tabelle (`0` e `1`) creati in precedenza.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     In fase di esecuzione è possibile utilizzare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo a cui associare il <xref:System.Windows.Forms.DataGrid> controllo a un'origine dati diversa. Ad esempio, è possibile disporre di più [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controlli di dati, ciascuno connesso a un database diverso.  
  
### <a name="to-change-the-datasource-programmatically"></a>Per modificare l'origine dati a livello di codice  
  
1.  Impostare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo per il nome dell'origine dati e della tabella che si desidera associare.  
  
     Nell'esempio seguente viene illustrato come modificare l'origine dati utilizzando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo da un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controllo dati (adoPubsAuthors) connesso alla tabella Authors del database Pubs.  
  
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
 [Set di dati ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Procedura: Associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
