---
title: 'Procedura: creare un progetto LINQ to DataSet in Visual Studio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3add191250a10d1d6016263ada0ba53fc8082717
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a><span data-ttu-id="04eef-102">Procedura: creare un progetto LINQ to DataSet in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04eef-102">How to: Create a LINQ to DataSet Project In Visual Studio</span></span>
<span data-ttu-id="04eef-103">I tipi diversi di progetti [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] richiedono determinati spazi dei nomi importati (Visual Basic) o direttive `using` (C#) e riferimenti.</span><span class="sxs-lookup"><span data-stu-id="04eef-103">The different types of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] projects require certain imported namespaces (Visual Basic) or `using` directives (C#) and references.</span></span> <span data-ttu-id="04eef-104">Il requisito minimo è un riferimento a System.Core.dll e una direttiva `using` per <xref:System.Linq>.</span><span class="sxs-lookup"><span data-stu-id="04eef-104">The minimum requirement is a reference to System.Core.dll and a `using` directive for <xref:System.Linq>.</span></span> <span data-ttu-id="04eef-105">Per impostazione predefinita, questi elementi vengono forniti se si crea un nuovo progetto di [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04eef-105">By default, these are supplied if you create a new [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)] project.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="04eef-106"> richiede anche un riferimento a System.Data.dll e System.Data.DataSetExtensions.dll e una direttiva `Imports` (Visual Basic) o `using` (C#).</span><span class="sxs-lookup"><span data-stu-id="04eef-106"> also requires a reference to System.Data.dll and System.Data.DataSetExtensions.dll and an `Imports` (Visual Basic) or `using` (C#) directive.</span></span>  
  
 <span data-ttu-id="04eef-107">Se un progetto viene aggiornato da una versione precedente di Visual Studio, può essere necessario specificare manualmente questi riferimenti correlati a LINQ.</span><span class="sxs-lookup"><span data-stu-id="04eef-107">If you are upgrading a project from an earlier version of Visual Studio, you might have to supply these LINQ-related references manually.</span></span> <span data-ttu-id="04eef-108">Può inoltre essere necessario impostare manualmente il progetto in modo che sia destinato a .NET Framework versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="04eef-108">You might also have to manually set the project to target the .NET Framework version 3.5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04eef-109">Se si sta compilando da un prompt dei comandi, è necessario fare manualmente riferimento DLL correlate a LINQ in `drive` **:**\Programmi\Reference Assemblies\Microsoft\Framework\v3.5.</span><span class="sxs-lookup"><span data-stu-id="04eef-109">If you are building from a command prompt, you must manually reference the LINQ-related DLLs in `drive`**:**\Program Files\Reference Assemblies\Microsoft\Framework\v3.5.</span></span>  
  
### <a name="to-target-the-net-framework-35"></a><span data-ttu-id="04eef-110">Per impostare .NET Framework 3.5 come destinazione</span><span class="sxs-lookup"><span data-stu-id="04eef-110">To target the .NET Framework 3.5</span></span>  
  
1.  <span data-ttu-id="04eef-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] creare un nuovo progetto di Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="04eef-111">In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)], create a new Visual Basic or C# project.</span></span> <span data-ttu-id="04eef-112">In alternativa, è possibile aprire un progetto di Visual Basic o C# creato in Visual Studio 2005 e seguire le istruzioni per convertirlo in un progetto di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04eef-112">Alternatively, you can open a Visual Basic or C# project that was created in Visual Studio 2005 and follow the prompts to convert it to a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="04eef-113">Per un progetto c#, fare clic su di **progetto** menu e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="04eef-113">For a C# project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="04eef-114">Nel **applicazione** selezionare .NET Framework 3.5 nella pagina delle proprietà di **Framework di destinazione** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="04eef-114">In the **Application** property page, select .NET Framework 3.5 in the **Target Framework** drop-down list.</span></span>  
  
3.  <span data-ttu-id="04eef-115">Per un progetto di Visual Basic, scegliere il **progetto** menu e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="04eef-115">For a Visual Basic project, click the **Project** menu, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="04eef-116">Nel **compilare** pagina delle proprietà, fare clic su **opzioni di compilazione avanzate** e quindi selezionare .NET Framework 3.5 nel **il Framework di destinazione (tutte le configurazioni)** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="04eef-116">In the **Compile** property page, click **Advanced Compile Options** and then select .NET Framework 3.5 in the **Target Framework (all configurations)** drop-down list.</span></span>  
  
4.  <span data-ttu-id="04eef-117">Nel **progetto** menu, fare clic su **Aggiungi riferimento**, fare clic sul **.NET** scheda, scorrere verso il basso **core**, selezionarlo e quindi fare clic su  **OK**.</span><span class="sxs-lookup"><span data-stu-id="04eef-117">On the **Project** menu, click **Add Reference**, click the **.NET** tab, scroll down to **System.Core**, click it, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="04eef-118">Aggiungere una direttiva `using` o uno spazio dei nomi importato per <xref:System.Linq> al progetto o al file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="04eef-118">Add a `using` directive or imported namespace for <xref:System.Linq> to your source code file or project.</span></span>  
  
     <span data-ttu-id="04eef-119">Per ulteriori informazioni, vedere [direttiva using](~/docs/csharp/language-reference/keywords/using-directive.md) o [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="04eef-119">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
### <a name="to-enable-linq-to-dataset-functionality"></a><span data-ttu-id="04eef-120">Per abilitare la funzionalità LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="04eef-120">To enable LINQ to DataSet functionality</span></span>  
  
1.  <span data-ttu-id="04eef-121">Se necessario, seguire i passaggi illustrati precedentemente in questo argomento per aggiungere un riferimento a System.Core.dll e una direttiva `using` o uno spazio dei nomi importato per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="04eef-121">If necessary, follow the steps earlier in this topic to add a reference to System.Core.dll and a `using` directive or imported namespace for System.Linq.</span></span>  
  
2.  <span data-ttu-id="04eef-122">In c# o Visual Basic, scegliere il **progetto** menu e quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="04eef-122">In C# or Visual Basic, click the **Project** menu, and then click **Add Reference**.</span></span>  
  
3.  <span data-ttu-id="04eef-123">Nel **Aggiungi riferimento** la finestra di dialogo, fare clic sul **.NET** scheda se non è in primo piano.</span><span class="sxs-lookup"><span data-stu-id="04eef-123">In the **Add Reference** dialog box, click the **.NET** tab if it is not on top.</span></span> <span data-ttu-id="04eef-124">Scorrere verso il basso **System. Data** e **DataSetExtensions** e fare clic su di essi.</span><span class="sxs-lookup"><span data-stu-id="04eef-124">Scroll down to **System.Data** and **System.Data.DataSetExtensions** and click on them.</span></span> <span data-ttu-id="04eef-125">Fare clic su di **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="04eef-125">Click the **OK** button.</span></span>  
  
4.  <span data-ttu-id="04eef-126">Aggiungere una direttiva `using` o uno spazio dei nomi importato per <xref:System.Data> al progetto o al file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="04eef-126">Add a `using` directive or imported namespace for <xref:System.Data> to your source code file or project.</span></span> <span data-ttu-id="04eef-127">Per ulteriori informazioni, vedere [direttiva using](~/docs/csharp/language-reference/keywords/using-directive.md) o [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="04eef-127">For more information, see [using Directive](~/docs/csharp/language-reference/keywords/using-directive.md) or [How to: Add or Remove Imported Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).</span></span>  
  
5.  <span data-ttu-id="04eef-128">Aggiungere un riferimento a System.Data.DataSetExtensions.dll per la funzionalità LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="04eef-128">Add a reference to System.Data.DataSetExtensions.dll for LINQ to Dataset functionality.</span></span> <span data-ttu-id="04eef-129">Aggiungere un riferimento a System.Data.dll, se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="04eef-129">Add a reference to System.Data.dll if it does not already exist.</span></span>  
  
6.  <span data-ttu-id="04eef-130">Facoltativamente, aggiungere una direttiva `using` o uno spazio dei nomi importato per `System.Data.Common` o `System.Data.SqlClient`, a seconda della modalità di connessione al database.</span><span class="sxs-lookup"><span data-stu-id="04eef-130">Optionally, add a `using` directive or imported namespace for `System.Data.Common` or `System.Data.SqlClient`, depending on how you connect to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04eef-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04eef-131">See Also</span></span>  
 [<span data-ttu-id="04eef-132">Introduzione</span><span class="sxs-lookup"><span data-stu-id="04eef-132">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [<span data-ttu-id="04eef-133">Nozioni di base su LINQ</span><span class="sxs-lookup"><span data-stu-id="04eef-133">Getting Started with LINQ</span></span>](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
