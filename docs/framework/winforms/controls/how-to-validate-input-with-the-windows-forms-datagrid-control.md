---
title: "Procedura: Convalidare l'Input con il controllo DataGrid di Windows Form"
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
ms.openlocfilehash: 84057a2d9709963c7a7302110ab11931b86fcad9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497626"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Procedura: Convalidare l'Input con il controllo DataGrid di Windows Form

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Sono disponibili due tipi di convalida dell'input per i moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo. Se l'utente tenta di immettere un valore di un tipo di dati accettabile per la cella, ad esempio una stringa in un numero intero, il nuovo valore non valido viene sostituito con il valore precedente. Questo tipo di convalida dell'input viene eseguito automaticamente e non può essere personalizzato.

L'altro tipo di convalida dell'input è utilizzabile per rifiutare tutti i dati non validi, ad esempio un valore 0 in un campo che deve essere maggiore o uguale a 1 o una stringa non corretta. Questa operazione viene eseguita nel set di dati scrivendo un gestore eventi per il <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging> evento. L'esempio seguente usa il <xref:System.Data.DataTable.ColumnChanging> evento perché il valore accettabile è ammesso in particolare per la colonna "Prodotto". È possibile usare il <xref:System.Data.DataTable.RowChanging> eventi per verificare che il valore di una colonna di "Data di fine" è successivo alla colonna "Data di inizio" nella stessa riga.

## <a name="to-validate-user-input"></a>Per convalidare l'input utente

1. Scrivere codice per gestire il <xref:System.Data.DataTable.ColumnChanging> eventi per la tabella appropriata. Quando viene rilevato un input, chiamare il <xref:System.Data.DataRow.SetColumnError%2A> metodo di <xref:System.Data.DataRow> oggetto.

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

    Sul posto il seguente codice all'interno di uno del form <xref:System.Windows.Forms.Form.Load> eventi o nel relativo costruttore.

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
- [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
