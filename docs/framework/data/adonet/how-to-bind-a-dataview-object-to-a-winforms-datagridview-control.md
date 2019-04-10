---
title: 'Procedura: Associare un oggetto DataView a un controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 7035c96208f6cad1f606727894e9d05aa51024a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342076"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="66c9f-102">Procedura: Associare un oggetto DataView a un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="66c9f-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="66c9f-103">Il controllo <xref:System.Windows.Forms.DataGridView> fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="66c9f-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="66c9f-104">Il controllo <xref:System.Windows.Forms.DataGridView> supporta il modello di data binding standard di Windows Form ed è quindi possibile associarlo a <xref:System.Data.DataView> e a varie altre origini dati.</span><span class="sxs-lookup"><span data-stu-id="66c9f-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="66c9f-105">Nella maggior parte dei casi, tuttavia, l'associazione viene eseguita a un componente <xref:System.Windows.Forms.BindingSource>, che gestisce i dettagli dell'interazione con l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="66c9f-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="66c9f-106">Per altre informazioni sul <xref:System.Windows.Forms.DataGridView> controllano, vedere [Cenni preliminari sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="66c9f-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="66c9f-107">Per connettere un controllo DataGridView a un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="66c9f-107">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="66c9f-108">Implementare un metodo per gestire i dettagli del recupero di dati da un database.</span><span class="sxs-lookup"><span data-stu-id="66c9f-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="66c9f-109">Nell'esempio di codice seguente viene implementato un metodo `GetData` che inizializza un componente <xref:System.Data.SqlClient.SqlDataAdapter> e lo usa per compilare <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="66c9f-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="66c9f-110">Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database.</span><span class="sxs-lookup"><span data-stu-id="66c9f-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="66c9f-111">Sarà necessario disporre di accesso a un server in cui sia installato il database SQL Server di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="66c9f-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="66c9f-112">Nel gestore eventi <xref:System.Windows.Forms.Form.Load> del form associare il controllo <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> e chiamare il metodo `GetData` per recuperare i dati dal database.</span><span class="sxs-lookup"><span data-stu-id="66c9f-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="66c9f-113">L'oggetto <xref:System.Data.DataView> viene creato da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sull'oggetto <xref:System.Data.DataTable> Contact e viene quindi associato al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="66c9f-113">The <xref:System.Data.DataView> is created from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="66c9f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66c9f-114">See also</span></span>

- [<span data-ttu-id="66c9f-115">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="66c9f-115">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
