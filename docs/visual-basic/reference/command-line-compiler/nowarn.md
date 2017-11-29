---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8da27ea2f9f0a4d370928d70cda1a796b822d97c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nowarn"></a><span data-ttu-id="46796-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="46796-102">/nowarn</span></span>
<span data-ttu-id="46796-103">Inibisce la capacità del compilatore di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="46796-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46796-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46796-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="46796-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="46796-105">Arguments</span></span>  
  
|<span data-ttu-id="46796-106">Termine</span><span class="sxs-lookup"><span data-stu-id="46796-106">Term</span></span>|<span data-ttu-id="46796-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="46796-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="46796-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="46796-108">Optional.</span></span> <span data-ttu-id="46796-109">Elenco delimitato da virgole dei numeri di ID di avviso che il compilatore deve eliminare.</span><span class="sxs-lookup"><span data-stu-id="46796-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="46796-110">Se non viene specificato l'ID di avviso, tutti gli avvisi vengono soppressi.</span><span class="sxs-lookup"><span data-stu-id="46796-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46796-111">Note</span><span class="sxs-lookup"><span data-stu-id="46796-111">Remarks</span></span>  
 <span data-ttu-id="46796-112">Il `/nowarn` opzione, il compilatore di non generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="46796-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="46796-113">Per eliminare un singolo avviso, specificare l'ID di avviso per il `/nowarn` opzione dopo la virgola.</span><span class="sxs-lookup"><span data-stu-id="46796-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="46796-114">Separare più numeri di avviso con virgole.</span><span class="sxs-lookup"><span data-stu-id="46796-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="46796-115">È necessario specificare solo la parte numerica dell'identificatore di avviso.</span><span class="sxs-lookup"><span data-stu-id="46796-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="46796-116">Ad esempio, se si desidera eliminare BC42024, l'avviso per le variabili locali inutilizzate, specificare `/nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="46796-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="46796-117">Per ulteriori informazioni sui numeri di ID avviso, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="46796-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="46796-118">Per impostare /nowarn in Visual Studio ambiente di sviluppo integrato.</span><span class="sxs-lookup"><span data-stu-id="46796-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="46796-119">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="46796-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="46796-120">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="46796-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="46796-121">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="46796-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="46796-122">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="46796-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="46796-123">3.  Selezionare il **Disabilita tutti gli avvisi** casella di controllo per disabilitare tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="46796-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="46796-124">-oppure-</span><span class="sxs-lookup"><span data-stu-id="46796-124">- or -</span></span><br />     <span data-ttu-id="46796-125">Per disabilitare un avviso specifico, fare clic su **Nessuno** dall'elenco a discesa adiacente all'avviso.</span><span class="sxs-lookup"><span data-stu-id="46796-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46796-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="46796-126">Example</span></span>  
 <span data-ttu-id="46796-127">Il codice seguente Compila `T2.vb` e non vengono visualizzati tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="46796-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="46796-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="46796-128">Example</span></span>  
 <span data-ttu-id="46796-129">Il codice seguente Compila `T2.vb` e non vengono visualizzati gli avvisi per le variabili locali inutilizzate (42024).</span><span class="sxs-lookup"><span data-stu-id="46796-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="46796-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46796-130">See Also</span></span>  
 [<span data-ttu-id="46796-131">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46796-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="46796-132">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="46796-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="46796-133">Configurazione degli avvisi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46796-133">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
