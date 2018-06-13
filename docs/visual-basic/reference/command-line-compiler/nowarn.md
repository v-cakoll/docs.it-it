---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 338b4672d215968275c30d37a2f8061e764aed8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653442"
---
# <a name="-nowarn"></a><span data-ttu-id="f0f29-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="f0f29-102">-nowarn</span></span>
<span data-ttu-id="f0f29-103">Inibisce la capacità del compilatore di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="f0f29-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f29-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0f29-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0f29-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f0f29-105">Arguments</span></span>  
  
|<span data-ttu-id="f0f29-106">Termine</span><span class="sxs-lookup"><span data-stu-id="f0f29-106">Term</span></span>|<span data-ttu-id="f0f29-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="f0f29-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="f0f29-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f0f29-108">Optional.</span></span> <span data-ttu-id="f0f29-109">Elenco delimitato da virgole dei numeri di ID di avviso che il compilatore deve eliminare.</span><span class="sxs-lookup"><span data-stu-id="f0f29-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="f0f29-110">Se non viene specificato l'ID di avviso, tutti gli avvisi vengono soppressi.</span><span class="sxs-lookup"><span data-stu-id="f0f29-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0f29-111">Note</span><span class="sxs-lookup"><span data-stu-id="f0f29-111">Remarks</span></span>  
 <span data-ttu-id="f0f29-112">Il `-nowarn` opzione, il compilatore di non generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="f0f29-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="f0f29-113">Per eliminare un singolo avviso, specificare l'ID di avviso per il `-nowarn` opzione dopo la virgola.</span><span class="sxs-lookup"><span data-stu-id="f0f29-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="f0f29-114">Separare più numeri di avviso con virgole.</span><span class="sxs-lookup"><span data-stu-id="f0f29-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="f0f29-115">È necessario specificare solo la parte numerica dell'identificatore di avviso.</span><span class="sxs-lookup"><span data-stu-id="f0f29-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="f0f29-116">Ad esempio, se si desidera eliminare BC42024, l'avviso per le variabili locali inutilizzate, specificare `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="f0f29-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="f0f29-117">Per ulteriori informazioni sui numeri di ID avviso, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f0f29-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="f0f29-118">Per impostare - nowarn nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f0f29-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f0f29-119">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="f0f29-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f0f29-120">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="f0f29-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f0f29-121">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="f0f29-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f0f29-122">3.  Selezionare il **Disabilita tutti gli avvisi** casella di controllo per disabilitare tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f0f29-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="f0f29-123">-oppure-</span><span class="sxs-lookup"><span data-stu-id="f0f29-123">- or -</span></span><br />     <span data-ttu-id="f0f29-124">Per disabilitare un avviso specifico, fare clic su **Nessuno** dall'elenco a discesa adiacente all'avviso.</span><span class="sxs-lookup"><span data-stu-id="f0f29-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f0f29-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0f29-125">Example</span></span>  
 <span data-ttu-id="f0f29-126">Il codice seguente Compila `T2.vb` e non vengono visualizzati tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="f0f29-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="f0f29-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0f29-127">Example</span></span>  
 <span data-ttu-id="f0f29-128">Il codice seguente Compila `T2.vb` e non vengono visualizzati gli avvisi per le variabili locali inutilizzate (42024).</span><span class="sxs-lookup"><span data-stu-id="f0f29-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0f29-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0f29-129">See Also</span></span>  
 [<span data-ttu-id="f0f29-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0f29-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f0f29-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f0f29-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="f0f29-132">Configurazione degli avvisi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0f29-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
