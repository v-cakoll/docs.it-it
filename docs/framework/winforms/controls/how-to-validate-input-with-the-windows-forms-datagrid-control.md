---
title: Convalidare l'input con il controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728291"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Procedura: convalidare l'input con il controllo DataGrid Windows Form

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Sono disponibili due tipi di convalida dell'input per il controllo Windows Forms <xref:System.Windows.Forms.DataGrid>. Se l'utente tenta di immettere un valore che è di un tipo di dati non accettabile per la cella, ad esempio una stringa in un numero intero, il nuovo valore non valido viene sostituito con il valore precedente. Questo tipo di convalida dell'input viene eseguito automaticamente e non può essere personalizzato.

L'altro tipo di convalida dell'input può essere usato per rifiutare eventuali dati non accettabili, ad esempio un valore 0 in un campo che deve essere maggiore o uguale a 1 o una stringa non appropriata. Questa operazione viene eseguita nel set di dati scrivendo un gestore eventi per l'evento <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging>. Nell'esempio seguente viene usato l'evento <xref:System.Data.DataTable.ColumnChanging> perché il valore non accettabile non è consentito per la colonna "Product" in particolare. È possibile utilizzare l'evento <xref:System.Data.DataTable.RowChanging> per verificare che il valore di una colonna "Data fine" sia successivo alla colonna "data di inizio" nella stessa riga.

## <a name="to-validate-user-input"></a>Per convalidare l'input dell'utente

1. Scrivere il codice per gestire l'evento <xref:System.Data.DataTable.ColumnChanging> per la tabella appropriata. Quando viene rilevato un input non appropriato, chiamare il metodo <xref:System.Data.DataRow.SetColumnError%2A> dell'oggetto <xref:System.Data.DataRow>.

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. Connettere il gestore eventi all'evento.

    Inserire il codice seguente all'interno dell'evento <xref:System.Windows.Forms.Form.Load> del form o del relativo costruttore.

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [Controllo DataGrid](datagrid-control-windows-forms.md)
