---
title: 'Procedura: creare un Form Master-Details mediante due controlli DataGridView di Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c724408ae689f339585267e183061f56b8271a9a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="f2928-102">Procedura: creare un form Master-Details mediante due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f2928-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="f2928-103">Nell'esempio di codice riportato di seguito viene creato un form Master-Details usando due controlli <xref:System.Windows.Forms.DataGridView> associati a due componenti <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="f2928-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="f2928-104">L'origine dati è un <xref:System.Data.DataSet> contenente le tabelle `Customers` e `Orders` del database di esempio SQL Server Northwind insieme a un oggetto <xref:System.Data.DataRelation> che mette in relazione le due tabelle tramite la colonna `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="f2928-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="f2928-105">Un oggetto <xref:System.Windows.Forms.BindingSource> è associato alla tabella `Customers` padre nel DataSet.</span><span class="sxs-lookup"><span data-stu-id="f2928-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="f2928-106">Questi dati vengono visualizzati nel controllo <xref:System.Windows.Forms.DataGridView> master.</span><span class="sxs-lookup"><span data-stu-id="f2928-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f2928-107">L'altro oggetto <xref:System.Windows.Forms.BindingSource> è associato al primo connettore dati.</span><span class="sxs-lookup"><span data-stu-id="f2928-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="f2928-108">Poiché la proprietà <xref:System.Windows.Forms.BindingSource.DataMember%2A> del secondo oggetto <xref:System.Windows.Forms.BindingSource> è impostata sul nome di <xref:System.Data.DataRelation>,</span><span class="sxs-lookup"><span data-stu-id="f2928-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="f2928-109">il controllo dettagli <xref:System.Windows.Forms.DataGridView> associato visualizza le righe della tabella `Orders` figlio corrispondenti alla riga corrente nel controllo <xref:System.Windows.Forms.DataGridView> master.</span><span class="sxs-lookup"><span data-stu-id="f2928-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="f2928-110">Per una spiegazione completa di questo esempio di codice, vedere [procedura dettagliata: creazione di un Master-Details Form utilizzando due Windows Form controlli DataGridView](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md).</span><span class="sxs-lookup"><span data-stu-id="f2928-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2928-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f2928-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2928-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f2928-112">Compiling the Code</span></span>  
 <span data-ttu-id="f2928-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2928-113">This example requires:</span></span>  
  
 <span data-ttu-id="f2928-114">Riferimenti agli assembly System, System.Data, System.Windows.Forms e System.XML.</span><span class="sxs-lookup"><span data-stu-id="f2928-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
-   <span data-ttu-id="f2928-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f2928-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f2928-116">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="f2928-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="f2928-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f2928-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f2928-118">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2928-118">.NET Framework Security</span></span>  
 <span data-ttu-id="f2928-119">L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2928-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="f2928-120">L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro.</span><span class="sxs-lookup"><span data-stu-id="f2928-120">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="f2928-121">Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="f2928-121">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2928-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2928-122">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="f2928-123">Procedura dettagliata: Creazione di un form Master-Details con due controlli DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f2928-123">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 [<span data-ttu-id="f2928-124">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f2928-124">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="f2928-125">Protezione delle informazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="f2928-125">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
