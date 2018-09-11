---
title: "Procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 17aff7073af336c0f32effc663eae5f11c194df2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44267882"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6ac0d-102">Procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ac0d-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6ac0d-103">Nell'esempio di codice seguente viene illustrato come usare il controllo <xref:System.Windows.Forms.DataGridView> per segnalare all'utente eventuali errori di immissione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="6ac0d-104">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ac0d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ac0d-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6ac0d-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="6ac0d-106">Compiling the Code</span></span>  
 <span data-ttu-id="6ac0d-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac0d-107">This example requires:</span></span>  
  
-   <span data-ttu-id="6ac0d-108">Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="6ac0d-109">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6ac0d-110">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6ac0d-111">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6ac0d-112">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ac0d-112">.NET Framework Security</span></span>  
 <span data-ttu-id="6ac0d-113">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="6ac0d-114">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="6ac0d-115">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-115">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac0d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ac0d-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="6ac0d-117">Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ac0d-117">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="6ac0d-118">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ac0d-118">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="6ac0d-119">Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ac0d-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="6ac0d-120">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="6ac0d-120">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
