---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 89f6566bd733ff92d464c026102429d3fc5cf0c1
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50047852"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="c58af-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c58af-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="c58af-103">Indica al compilatore di considerare la prima occorrenza di un avviso come errore.</span><span class="sxs-lookup"><span data-stu-id="c58af-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c58af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c58af-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c58af-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c58af-105">Arguments</span></span>  
  
|<span data-ttu-id="c58af-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c58af-106">Term</span></span>|<span data-ttu-id="c58af-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c58af-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c58af-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="c58af-108">+ &#124; -</span></span>|<span data-ttu-id="c58af-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c58af-109">Optional.</span></span> <span data-ttu-id="c58af-110">Per impostazione predefinita, `-warnaserror-` è attivo, gli avvisi non impedire al compilatore che produce un file di output.</span><span class="sxs-lookup"><span data-stu-id="c58af-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="c58af-111">Il `-warnaserror` opzione, ovvero lo stesso come `-warnaserror+`, gli avvisi vengono considerati come errori.</span><span class="sxs-lookup"><span data-stu-id="c58af-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="c58af-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c58af-112">Optional.</span></span> <span data-ttu-id="c58af-113">Elenco delimitato da virgole di ID avviso numeri a cui il `-warnaserror` opzione è valida.</span><span class="sxs-lookup"><span data-stu-id="c58af-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="c58af-114">Se non viene specificato alcun ID di avviso, il `-warnaserror` opzione si applica a tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c58af-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c58af-115">Note</span><span class="sxs-lookup"><span data-stu-id="c58af-115">Remarks</span></span>  
 <span data-ttu-id="c58af-116">Il `-warnaserror` opzione Considera tutti gli avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="c58af-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="c58af-117">I messaggi che in genere vengono segnalati come avvisi sono invece segnalati come errori.</span><span class="sxs-lookup"><span data-stu-id="c58af-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="c58af-118">Il compilatore segnala le occorrenze successive dello stesso avviso come avvisi.</span><span class="sxs-lookup"><span data-stu-id="c58af-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="c58af-119">Per impostazione predefinita, `-warnaserror-` è attiva, pertanto gli avvisi come messaggio informativo solo.</span><span class="sxs-lookup"><span data-stu-id="c58af-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="c58af-120">Il `-warnaserror` opzione, ovvero lo stesso come `-warnaserror+`, gli avvisi vengono considerati come errori.</span><span class="sxs-lookup"><span data-stu-id="c58af-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="c58af-121">Se si desidera che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole di numeri di avvisi da considerare come errori.</span><span class="sxs-lookup"><span data-stu-id="c58af-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c58af-122">Il `-warnaserror` opzione non controlla come vengono visualizzati gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c58af-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="c58af-123">Usare la [- nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opzione per disabilitare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c58af-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="c58af-124">Per impostare - warnaserror considerare tutti gli avvisi come errori nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c58af-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c58af-125">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="c58af-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c58af-126">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c58af-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c58af-127">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="c58af-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c58af-128">3.  Assicurarsi che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="c58af-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="c58af-129">4.  Verificare i **considera tutti gli avvisi come errori** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="c58af-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="c58af-130">Per impostare - warnaserror specifico considerarli come errori nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c58af-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c58af-131">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="c58af-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c58af-132">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c58af-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="c58af-133">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="c58af-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c58af-134">3.  Assicurarsi che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="c58af-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="c58af-135">4.  Assicurarsi che il **considera tutti gli avvisi come errori** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="c58af-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="c58af-136">5.  Selezionare **errore** dalle **notifica** colonna adiacente all'avviso che deve essere considerato come un errore.</span><span class="sxs-lookup"><span data-stu-id="c58af-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c58af-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="c58af-137">Example</span></span>  
 <span data-ttu-id="c58af-138">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare un errore per la prima occorrenza di ogni avviso generato.</span><span class="sxs-lookup"><span data-stu-id="c58af-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="c58af-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="c58af-139">Example</span></span>  
 <span data-ttu-id="c58af-140">Il codice seguente Compila `T2.vb` ed espone un solo avviso per visualizzare le variabili locali inutilizzate (42024) come un errore.</span><span class="sxs-lookup"><span data-stu-id="c58af-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c58af-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c58af-141">See Also</span></span>  
 [<span data-ttu-id="c58af-142">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c58af-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c58af-143">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c58af-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c58af-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c58af-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
