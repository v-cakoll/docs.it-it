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
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="cf46a-102">Procedura: convalidare l'input con il controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="cf46a-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="cf46a-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cf46a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="cf46a-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="cf46a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="cf46a-105">Sono disponibili due tipi di convalida dell'input per il controllo Windows Forms <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="cf46a-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="cf46a-106">Se l'utente tenta di immettere un valore che è di un tipo di dati non accettabile per la cella, ad esempio una stringa in un numero intero, il nuovo valore non valido viene sostituito con il valore precedente.</span><span class="sxs-lookup"><span data-stu-id="cf46a-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="cf46a-107">Questo tipo di convalida dell'input viene eseguito automaticamente e non può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cf46a-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="cf46a-108">L'altro tipo di convalida dell'input può essere usato per rifiutare eventuali dati non accettabili, ad esempio un valore 0 in un campo che deve essere maggiore o uguale a 1 o una stringa non appropriata.</span><span class="sxs-lookup"><span data-stu-id="cf46a-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="cf46a-109">Questa operazione viene eseguita nel set di dati scrivendo un gestore eventi per l'evento <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging>.</span><span class="sxs-lookup"><span data-stu-id="cf46a-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="cf46a-110">Nell'esempio seguente viene usato l'evento <xref:System.Data.DataTable.ColumnChanging> perché il valore non accettabile non è consentito per la colonna "Product" in particolare.</span><span class="sxs-lookup"><span data-stu-id="cf46a-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="cf46a-111">È possibile utilizzare l'evento <xref:System.Data.DataTable.RowChanging> per verificare che il valore di una colonna "Data fine" sia successivo alla colonna "data di inizio" nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="cf46a-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="cf46a-112">Per convalidare l'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="cf46a-112">To validate user input</span></span>

1. <span data-ttu-id="cf46a-113">Scrivere il codice per gestire l'evento <xref:System.Data.DataTable.ColumnChanging> per la tabella appropriata.</span><span class="sxs-lookup"><span data-stu-id="cf46a-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="cf46a-114">Quando viene rilevato un input non appropriato, chiamare il metodo <xref:System.Data.DataRow.SetColumnError%2A> dell'oggetto <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="cf46a-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

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

2. <span data-ttu-id="cf46a-115">Connettere il gestore eventi all'evento.</span><span class="sxs-lookup"><span data-stu-id="cf46a-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="cf46a-116">Inserire il codice seguente all'interno dell'evento <xref:System.Windows.Forms.Form.Load> del form o del relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="cf46a-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cf46a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf46a-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="cf46a-118">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="cf46a-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
