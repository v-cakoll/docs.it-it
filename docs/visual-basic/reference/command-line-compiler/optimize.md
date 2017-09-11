---
title: /optimize | Documenti di Microsoft
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
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
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
ms.openlocfilehash: f01ab17d4a2f5d123538294a7a13d7a6d7a40267
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="optimize"></a><span data-ttu-id="dce1a-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="dce1a-102">/optimize</span></span>
<span data-ttu-id="dce1a-103">Abilita o disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dce1a-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dce1a-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="dce1a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dce1a-105">Arguments</span></span>  
  
|<span data-ttu-id="dce1a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="dce1a-106">Term</span></span>|<span data-ttu-id="dce1a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="dce1a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="dce1a-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="dce1a-108">`+` &#124; `-`</span></span>|<span data-ttu-id="dce1a-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dce1a-109">Optional.</span></span> <span data-ttu-id="dce1a-110">Il `/optimize-` opzione Disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dce1a-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="dce1a-111">Il `/optimize+` opzione consente di abilitarle.</span><span class="sxs-lookup"><span data-stu-id="dce1a-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="dce1a-112">Per impostazione predefinita, le ottimizzazioni vengono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="dce1a-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dce1a-113">Note</span><span class="sxs-lookup"><span data-stu-id="dce1a-113">Remarks</span></span>  
 <span data-ttu-id="dce1a-114">Le ottimizzazioni del compilatore rendono il file di output più piccolo, veloce e più efficiente.</span><span class="sxs-lookup"><span data-stu-id="dce1a-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="dce1a-115">Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `/optimize+` può rendere difficoltoso il debug.</span><span class="sxs-lookup"><span data-stu-id="dce1a-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="dce1a-116">Tutti i moduli generati con `/target:module` per un assembly deve utilizzare lo stesso `/optimize` le impostazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dce1a-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="dce1a-117">Per ulteriori informazioni, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="dce1a-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="dce1a-118">È possibile combinare il `/optimize` e `/debug` opzioni.</span><span class="sxs-lookup"><span data-stu-id="dce1a-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="dce1a-119">Per impostare /optimize nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dce1a-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="dce1a-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="dce1a-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="dce1a-121">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dce1a-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="dce1a-122">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="dce1a-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="dce1a-123">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="dce1a-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="dce1a-124">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="dce1a-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="dce1a-125">4.  Modificare il **abilita ottimizzazioni** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="dce1a-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dce1a-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="dce1a-126">Example</span></span>  
 <span data-ttu-id="dce1a-127">Il codice seguente Compila `T2.vb` e le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="dce1a-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="dce1a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dce1a-128">See Also</span></span>  
 <span data-ttu-id="dce1a-129">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="dce1a-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="dce1a-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="dce1a-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="dce1a-131"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="dce1a-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="dce1a-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span><span class="sxs-lookup"><span data-stu-id="dce1a-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span></span>
