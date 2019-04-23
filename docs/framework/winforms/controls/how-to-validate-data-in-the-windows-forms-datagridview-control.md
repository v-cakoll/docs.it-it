---
title: 'Procedura: Convalidare i dati nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: dae254c14790841b37162fca9f998be429006125
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225612"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3a2f3-102">Procedura: Convalidare i dati nel controllo DataGridView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3a2f3-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3a2f3-103">Nell'esempio di codice seguente viene illustrato come convalidare i dati immessi da un utente in un controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3a2f3-104">In questo esempio il controllo <xref:System.Windows.Forms.DataGridView> viene compilato con righe della tabella `Customers` del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="3a2f3-105">Quando l'utente modifica una cella nella colonna `CompanyName`, viene verificato che il valore non sia vuoto e che sia valido.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="3a2f3-106">Se il gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellValidating> rileva che il valore è una stringa vuota, il controllo <xref:System.Windows.Forms.DataGridView> impedisce all'utente di uscire dalla cella fino a quando non immette una stringa non vuota.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="3a2f3-107">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: Convalida dei dati in di Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="3a2f3-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a2f3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a2f3-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a2f3-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3a2f3-109">Compiling the Code</span></span>  
 <span data-ttu-id="3a2f3-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a2f3-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3a2f3-111">Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="3a2f3-112">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3a2f3-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3a2f3-113">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3a2f3-114">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3a2f3-114">.NET Framework Security</span></span>  
 <span data-ttu-id="3a2f3-115">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-115">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3a2f3-116">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="3a2f3-116">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="3a2f3-117">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="3a2f3-117">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a2f3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a2f3-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="3a2f3-119">Procedura dettagliata: La convalida dei dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="3a2f3-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3a2f3-120">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3a2f3-120">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3a2f3-121">Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="3a2f3-121">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="3a2f3-122">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="3a2f3-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
