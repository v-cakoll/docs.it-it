---
title: 'Procedura: condividere dati associati tra form tramite il componente BindingSource'
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
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 95fd7583e6d86aa84c53f6cee7056f1d631e948b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="03298-102">Procedura: condividere dati associati tra form tramite il componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="03298-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="03298-103">È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="03298-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="03298-104">Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="03298-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="03298-105">L'esempio illustra questo scenario.</span><span class="sxs-lookup"><span data-stu-id="03298-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03298-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="03298-106">Example</span></span>  
 <span data-ttu-id="03298-107">L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form.</span><span class="sxs-lookup"><span data-stu-id="03298-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="03298-108">In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio.</span><span class="sxs-lookup"><span data-stu-id="03298-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="03298-109">Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.</span><span class="sxs-lookup"><span data-stu-id="03298-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03298-110">Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati</span><span class="sxs-lookup"><span data-stu-id="03298-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="03298-111">Per altre informazioni sul motivo per cui questa operazione viene eseguita, vedere [Procedura: Garantire la sincronizzazione di più controlli associati alla stessa origine dati](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="03298-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03298-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="03298-112">Compiling the Code</span></span>  
 <span data-ttu-id="03298-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="03298-113">This example requires:</span></span>  
  
-   <span data-ttu-id="03298-114">Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="03298-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="03298-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="03298-115">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="03298-116">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="03298-116">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="03298-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Forms completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="03298-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03298-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03298-118">See Also</span></span>  
 [<span data-ttu-id="03298-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="03298-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="03298-120">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="03298-120">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="03298-121">Procedura: gestire gli errori e le eccezioni che si verificano con l'associazione dati</span><span class="sxs-lookup"><span data-stu-id="03298-121">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
