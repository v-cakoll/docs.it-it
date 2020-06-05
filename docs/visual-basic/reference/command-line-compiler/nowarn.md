---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 37851f99eb88543e939ce48995ded41958e57cc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397488"
---
# <a name="-nowarn"></a><span data-ttu-id="04f35-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="04f35-102">-nowarn</span></span>
<span data-ttu-id="04f35-103">Inibisce la capacità del compilatore di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="04f35-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04f35-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="04f35-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="04f35-105">Arguments</span></span>  
  
|<span data-ttu-id="04f35-106">Termine</span><span class="sxs-lookup"><span data-stu-id="04f35-106">Term</span></span>|<span data-ttu-id="04f35-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="04f35-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="04f35-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="04f35-108">Optional.</span></span> <span data-ttu-id="04f35-109">Elenco delimitato da virgole dei numeri di ID avviso che il compilatore deve escludere.</span><span class="sxs-lookup"><span data-stu-id="04f35-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="04f35-110">Se gli ID avviso non vengono specificati, vengono eliminati tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="04f35-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04f35-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="04f35-111">Remarks</span></span>  
 <span data-ttu-id="04f35-112">L' `-nowarn` opzione fa sì che il compilatore non generi avvisi.</span><span class="sxs-lookup"><span data-stu-id="04f35-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="04f35-113">Per escludere un singolo avviso, fornire l'ID avviso all' `-nowarn` opzione che segue i due punti.</span><span class="sxs-lookup"><span data-stu-id="04f35-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="04f35-114">Separare più numeri di avviso con virgole.</span><span class="sxs-lookup"><span data-stu-id="04f35-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="04f35-115">È necessario specificare solo la parte numerica dell'identificatore di avviso.</span><span class="sxs-lookup"><span data-stu-id="04f35-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="04f35-116">Se ad esempio si desidera disattivare BC42024, viene visualizzato l'avviso relativo alle variabili locali non utilizzate `-nowarn:42024` .</span><span class="sxs-lookup"><span data-stu-id="04f35-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="04f35-117">Per ulteriori informazioni sui numeri ID avviso, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="04f35-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="04f35-118">Per impostare-nowarn in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="04f35-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="04f35-119">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="04f35-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="04f35-120">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="04f35-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="04f35-121">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="04f35-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="04f35-122">3. Selezionare la casella di controllo **Disabilita tutti gli avvisi** per disabilitare tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="04f35-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="04f35-123">- oppure -</span><span class="sxs-lookup"><span data-stu-id="04f35-123">- or -</span></span><br />     <span data-ttu-id="04f35-124">Per disabilitare un avviso particolare, fare clic su **nessuno** nell'elenco a discesa accanto all'avviso.</span><span class="sxs-lookup"><span data-stu-id="04f35-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="04f35-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="04f35-125">Example</span></span>  
 <span data-ttu-id="04f35-126">Il codice seguente compila `T2.vb` e non visualizza alcun avviso.</span><span class="sxs-lookup"><span data-stu-id="04f35-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="04f35-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="04f35-127">Example</span></span>  
 <span data-ttu-id="04f35-128">Il codice seguente compila `T2.vb` e non Visualizza gli avvisi per le variabili locali non usate (42024).</span><span class="sxs-lookup"><span data-stu-id="04f35-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="04f35-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04f35-129">See also</span></span>

- [<span data-ttu-id="04f35-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04f35-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="04f35-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="04f35-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="04f35-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04f35-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
