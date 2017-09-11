---
title: /warnaserror (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8ed72415a75860b34e37c2bf4fc686cdae37f69e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="781a0-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="781a0-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="781a0-103">Indica al compilatore di considerare la prima occorrenza di un avviso come errore.</span><span class="sxs-lookup"><span data-stu-id="781a0-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="781a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="781a0-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="781a0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="781a0-105">Arguments</span></span>  
  
|<span data-ttu-id="781a0-106">Termine</span><span class="sxs-lookup"><span data-stu-id="781a0-106">Term</span></span>|<span data-ttu-id="781a0-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="781a0-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="781a0-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="781a0-108">+ &#124; -</span></span>|<span data-ttu-id="781a0-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="781a0-109">Optional.</span></span> <span data-ttu-id="781a0-110">Per impostazione predefinita, `/warnaserror-` è attivo, gli avvisi non impediscono il compilatore dalla produzione di un file di output.</span><span class="sxs-lookup"><span data-stu-id="781a0-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="781a0-111">Il `/warnaserror` opzione, ovvero lo stesso come `/warnaserror+`, gli avvisi vengono considerati come errori.</span><span class="sxs-lookup"><span data-stu-id="781a0-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="781a0-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="781a0-112">Optional.</span></span> <span data-ttu-id="781a0-113">Elenco delimitato da virgole di ID di avviso di numeri a cui il `/warnaserror` opzione si applica.</span><span class="sxs-lookup"><span data-stu-id="781a0-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="781a0-114">Se è specificato alcun ID avviso, il `/warnaserror` opzione si applica a tutti gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="781a0-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="781a0-115">Note</span><span class="sxs-lookup"><span data-stu-id="781a0-115">Remarks</span></span>  
 <span data-ttu-id="781a0-116">Il `/warnaserror` opzione Considera tutti gli avvisi come errori.</span><span class="sxs-lookup"><span data-stu-id="781a0-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="781a0-117">I messaggi che verranno in genere segnalati come avvisi vengono invece segnalati come errori.</span><span class="sxs-lookup"><span data-stu-id="781a0-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="781a0-118">Il compilatore segnala le occorrenze successive dello stesso avviso come avvisi.</span><span class="sxs-lookup"><span data-stu-id="781a0-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="781a0-119">Per impostazione predefinita, `/warnaserror-` è attiva, pertanto gli avvisi per essere esclusivamente informativi.</span><span class="sxs-lookup"><span data-stu-id="781a0-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="781a0-120">Il `/warnaserror` opzione, ovvero lo stesso come `/warnaserror+`, gli avvisi vengono considerati come errori.</span><span class="sxs-lookup"><span data-stu-id="781a0-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="781a0-121">Se si desidera che solo determinati avvisi vengano considerati errori, è possibile specificare un elenco delimitato da virgole dei numeri degli avvisi da considerare come errori.</span><span class="sxs-lookup"><span data-stu-id="781a0-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="781a0-122">Il `/warnaserror` opzione controlla la modalità di visualizzazione degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="781a0-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="781a0-123">Utilizzare il [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) opzione per disattivare gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="781a0-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="781a0-124">Per impostare /warnaserror considerare tutti gli avvisi come errori nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="781a0-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="781a0-125">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="781a0-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="781a0-126">Nel **Project** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="781a0-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="781a0-127">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="781a0-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="781a0-128">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="781a0-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="781a0-129">3.  Assicurarsi che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="781a0-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="781a0-130">4.  Controllare il **considera tutti gli avvisi come errori** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="781a0-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="781a0-131">Per impostare /warnaserror specifici avvisi vengano considerati come errori nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="781a0-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="781a0-132">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="781a0-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="781a0-133">Nel **Project** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="781a0-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="781a0-134">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="781a0-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="781a0-135">3.  Assicurarsi che il **Disabilita tutti gli avvisi** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="781a0-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="781a0-136">4.  Assicurarsi che il **considera tutti gli avvisi come errori** casella di controllo è deselezionata.</span><span class="sxs-lookup"><span data-stu-id="781a0-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="781a0-137">5.  Selezionare **errore** dal **notifica** colonna adiacente all'avviso che deve essere considerato come un errore.</span><span class="sxs-lookup"><span data-stu-id="781a0-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="781a0-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="781a0-138">Example</span></span>  
 <span data-ttu-id="781a0-139">Il codice seguente Compila `In.vb` viene visualizzato un errore per la prima occorrenza di ogni avviso generato.</span><span class="sxs-lookup"><span data-stu-id="781a0-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="781a0-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="781a0-140">Example</span></span>  
 <span data-ttu-id="781a0-141">Il codice seguente Compila `T2.vb` e viene considerato come un errore solo l'avviso per le variabili locali inutilizzate (42024).</span><span class="sxs-lookup"><span data-stu-id="781a0-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="781a0-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="781a0-142">See Also</span></span>  
 <span data-ttu-id="781a0-143">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="781a0-143">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="781a0-144"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="781a0-144"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="781a0-145"> [Configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="781a0-145"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
