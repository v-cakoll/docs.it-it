---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a><span data-ttu-id="d9c7d-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="d9c7d-102">/optimize</span></span>
<span data-ttu-id="d9c7d-103">Abilita o disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9c7d-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9c7d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d9c7d-105">Arguments</span></span>  
  
|<span data-ttu-id="d9c7d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d9c7d-106">Term</span></span>|<span data-ttu-id="d9c7d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d9c7d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d9c7d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d9c7d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d9c7d-109">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-109">Optional.</span></span> <span data-ttu-id="d9c7d-110">Il `/optimize-` opzione Disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="d9c7d-111">Il `/optimize+` opzione consente di abilitarle.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="d9c7d-112">Per impostazione predefinita, le ottimizzazioni sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9c7d-113">Note</span><span class="sxs-lookup"><span data-stu-id="d9c7d-113">Remarks</span></span>  
 <span data-ttu-id="d9c7d-114">Le ottimizzazioni del compilatore verificare il file di output più piccoli, più veloce e più efficiente.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="d9c7d-115">Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `/optimize+` può rendere difficile il debug.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="d9c7d-116">Tutti i moduli generati con `/target:module` per un assembly deve utilizzare lo stesso `/optimize` le impostazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="d9c7d-117">Per ulteriori informazioni, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="d9c7d-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="d9c7d-118">È possibile combinare la `/optimize` e `/debug` opzioni.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="d9c7d-119">Per impostare /optimize nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9c7d-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d9c7d-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d9c7d-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="d9c7d-122">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="d9c7d-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="d9c7d-123">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d9c7d-124">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="d9c7d-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d9c7d-125">4.  Modificare il **abilitare le ottimizzazioni** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d9c7d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9c7d-126">Example</span></span>  
 <span data-ttu-id="d9c7d-127">Il codice seguente Compila `T2.vb` e abilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d9c7d-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9c7d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9c7d-128">See Also</span></span>  
 [<span data-ttu-id="d9c7d-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9c7d-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d9c7d-130">/debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c7d-130">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="d9c7d-131">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d9c7d-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d9c7d-132">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c7d-132">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
