---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005393"
---
# <a name="-nowarn"></a><span data-ttu-id="6109b-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6109b-102">-nowarn</span></span>
<span data-ttu-id="6109b-103">Inibisce la capacità del compilatore di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="6109b-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6109b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6109b-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6109b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6109b-105">Arguments</span></span>  
  
|<span data-ttu-id="6109b-106">Nome</span><span class="sxs-lookup"><span data-stu-id="6109b-106">Term</span></span>|<span data-ttu-id="6109b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6109b-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="6109b-108">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6109b-108">Optional.</span></span> <span data-ttu-id="6109b-109">Elenco delimitato da virgole dei numeri di ID avviso che il compilatore deve escludere.</span><span class="sxs-lookup"><span data-stu-id="6109b-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="6109b-110">Se gli ID avviso non vengono specificati, vengono eliminati tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6109b-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6109b-111">Note</span><span class="sxs-lookup"><span data-stu-id="6109b-111">Remarks</span></span>  
 <span data-ttu-id="6109b-112">L'opzione `-nowarn` impedisce al compilatore di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="6109b-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="6109b-113">Per escludere un singolo avviso, fornire l'ID avviso all'opzione `-nowarn` che segue i due punti.</span><span class="sxs-lookup"><span data-stu-id="6109b-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="6109b-114">Separare più numeri di avviso con virgole.</span><span class="sxs-lookup"><span data-stu-id="6109b-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="6109b-115">È necessario specificare solo la parte numerica dell'identificatore di avviso.</span><span class="sxs-lookup"><span data-stu-id="6109b-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="6109b-116">Ad esempio, se si desidera disattivare BC42024, l'avviso per le variabili locali non usate, specificare `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="6109b-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="6109b-117">Per ulteriori informazioni sui numeri ID avviso, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6109b-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="6109b-118">Per impostare-nowarn in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="6109b-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6109b-119">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6109b-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6109b-120">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6109b-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6109b-121">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="6109b-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6109b-122">3.  Selezionare la casella di controllo **Disabilita tutti gli avvisi** per disabilitare tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="6109b-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="6109b-123">-oppure-</span><span class="sxs-lookup"><span data-stu-id="6109b-123">- or -</span></span><br />     <span data-ttu-id="6109b-124">Per disabilitare un avviso particolare, fare clic su **nessuno** nell'elenco a discesa accanto all'avviso.</span><span class="sxs-lookup"><span data-stu-id="6109b-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6109b-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="6109b-125">Example</span></span>  
 <span data-ttu-id="6109b-126">Il codice seguente compila `T2.vb` e non visualizza alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="6109b-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="6109b-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="6109b-127">Example</span></span>  
 <span data-ttu-id="6109b-128">Il codice seguente compila `T2.vb` e non Visualizza gli avvisi per le variabili locali non usate (42024).</span><span class="sxs-lookup"><span data-stu-id="6109b-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6109b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6109b-129">See also</span></span>

- [<span data-ttu-id="6109b-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6109b-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6109b-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6109b-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6109b-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6109b-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
