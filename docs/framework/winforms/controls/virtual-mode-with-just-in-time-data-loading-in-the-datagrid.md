---
title: 'Procedura: implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: c5b218786d2b52037ec9009ac9fd68c089b1bb47
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081148"
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5f54a-102">Procedura: implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f54a-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5f54a-103">Il seguente esempio di codice mostra come usare la modalità virtuale nel controllo <xref:System.Windows.Forms.DataGridView> con una cache dei dati che carica i dati da un server solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="5f54a-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="5f54a-104">In questo esempio viene descritto dettagliatamente [implementazione della modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="5f54a-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f54a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f54a-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5f54a-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5f54a-106">Compiling the Code</span></span>  
 <span data-ttu-id="5f54a-107">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f54a-107">This example requires:</span></span>  
  
-   <span data-ttu-id="5f54a-108">Riferimenti agli assembly System, System.Data, System.Xml e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5f54a-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="5f54a-109">Accesso a un server in cui sia installato il database SQL Server di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="5f54a-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="5f54a-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5f54a-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5f54a-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="5f54a-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="5f54a-112">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="5f54a-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5f54a-113">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5f54a-113">.NET Framework Security</span></span>  
 <span data-ttu-id="5f54a-114">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5f54a-114">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="5f54a-115">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="5f54a-115">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="5f54a-116">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="5f54a-116">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f54a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f54a-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 [<span data-ttu-id="5f54a-118">Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f54a-118">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="5f54a-119">Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f54a-119">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="5f54a-120">Modo virtuale nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f54a-120">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
