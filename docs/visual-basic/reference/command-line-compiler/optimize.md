---
title: -ottimizzare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7df1c873c166def9fde1bedc139470263e3e4437
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-optimize"></a><span data-ttu-id="14fe8-102">-ottimizzare</span><span class="sxs-lookup"><span data-stu-id="14fe8-102">-optimize</span></span>
<span data-ttu-id="14fe8-103">Abilita o disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="14fe8-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fe8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14fe8-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="14fe8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="14fe8-105">Arguments</span></span>  
  
|<span data-ttu-id="14fe8-106">Termine</span><span class="sxs-lookup"><span data-stu-id="14fe8-106">Term</span></span>|<span data-ttu-id="14fe8-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="14fe8-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="14fe8-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="14fe8-108">`+` &#124; `-`</span></span>|<span data-ttu-id="14fe8-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="14fe8-109">Optional.</span></span> <span data-ttu-id="14fe8-110">Il `-optimize-` opzione Disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="14fe8-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="14fe8-111">Il `-optimize+` opzione consente di abilitarle.</span><span class="sxs-lookup"><span data-stu-id="14fe8-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="14fe8-112">Per impostazione predefinita, le ottimizzazioni sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="14fe8-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14fe8-113">Note</span><span class="sxs-lookup"><span data-stu-id="14fe8-113">Remarks</span></span>  
 <span data-ttu-id="14fe8-114">Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="14fe8-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="14fe8-115">Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `-optimize+` può rendere difficile il debug.</span><span class="sxs-lookup"><span data-stu-id="14fe8-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="14fe8-116">Tutti i moduli generati con `-target:module` per un assembly deve utilizzare lo stesso `-optimize` le impostazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="14fe8-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="14fe8-117">Per altre informazioni, vedere [-destinazione (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="14fe8-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="14fe8-118">È possibile combinare la `-optimize` e `-debug` opzioni.</span><span class="sxs-lookup"><span data-stu-id="14fe8-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="14fe8-119">Per impostare - ottimizzare nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14fe8-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="14fe8-120">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="14fe8-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="14fe8-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="14fe8-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="14fe8-122">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="14fe8-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="14fe8-123">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="14fe8-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="14fe8-124">4.  Modificare il **abilitare le ottimizzazioni** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="14fe8-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14fe8-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="14fe8-125">Example</span></span>  
 <span data-ttu-id="14fe8-126">Il codice seguente Compila `T2.vb` e abilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="14fe8-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="14fe8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14fe8-127">See Also</span></span>  
 [<span data-ttu-id="14fe8-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14fe8-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="14fe8-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14fe8-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="14fe8-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="14fe8-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="14fe8-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14fe8-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
