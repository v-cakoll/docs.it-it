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
ms.openlocfilehash: dc8c8f157e6673c1bddc68bfb511683e6d2b99be
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720332"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="14620-102">Procedura: Convalidare l'Input con il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="14620-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="14620-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="14620-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="14620-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="14620-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="14620-105">Sono disponibili due tipi di convalida dell'input per i moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="14620-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="14620-106">Se l'utente tenta di immettere un valore di un tipo di dati accettabile per la cella, ad esempio una stringa in un numero intero, il nuovo valore non valido viene sostituito con il valore precedente.</span><span class="sxs-lookup"><span data-stu-id="14620-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="14620-107">Questo tipo di convalida dell'input viene eseguito automaticamente e non può essere personalizzato.</span><span class="sxs-lookup"><span data-stu-id="14620-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="14620-108">L'altro tipo di convalida dell'input è utilizzabile per rifiutare tutti i dati non validi, ad esempio un valore 0 in un campo che deve essere maggiore o uguale a 1 o una stringa non corretta.</span><span class="sxs-lookup"><span data-stu-id="14620-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="14620-109">Questa operazione viene eseguita nel set di dati scrivendo un gestore eventi per il <xref:System.Data.DataTable.ColumnChanging> o <xref:System.Data.DataTable.RowChanging> evento.</span><span class="sxs-lookup"><span data-stu-id="14620-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="14620-110">L'esempio seguente usa il <xref:System.Data.DataTable.ColumnChanging> evento perché il valore accettabile è ammesso in particolare per la colonna "Prodotto".</span><span class="sxs-lookup"><span data-stu-id="14620-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="14620-111">È possibile usare il <xref:System.Data.DataTable.RowChanging> eventi per verificare che il valore di una colonna di "Data di fine" è successivo alla colonna "Data di inizio" nella stessa riga.</span><span class="sxs-lookup"><span data-stu-id="14620-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="14620-112">Per convalidare l'input utente</span><span class="sxs-lookup"><span data-stu-id="14620-112">To validate user input</span></span>

1. <span data-ttu-id="14620-113">Scrivere codice per gestire il <xref:System.Data.DataTable.ColumnChanging> eventi per la tabella appropriata.</span><span class="sxs-lookup"><span data-stu-id="14620-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="14620-114">Quando viene rilevato un input, chiamare il <xref:System.Data.DataRow.SetColumnError%2A> metodo di <xref:System.Data.DataRow> oggetto.</span><span class="sxs-lookup"><span data-stu-id="14620-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

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

2. <span data-ttu-id="14620-115">Connettere il gestore eventi all'evento.</span><span class="sxs-lookup"><span data-stu-id="14620-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="14620-116">Sul posto il seguente codice all'interno di uno del form <xref:System.Windows.Forms.Form.Load> eventi o nel relativo costruttore.</span><span class="sxs-lookup"><span data-stu-id="14620-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="14620-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14620-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="14620-118">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="14620-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
