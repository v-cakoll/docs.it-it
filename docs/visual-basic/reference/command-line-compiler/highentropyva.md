---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d40e5acda73786ee88d16bacd9bc5f69400be8
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="325ab-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="325ab-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="325ab-103">Indica se un eseguibile a 64 bit o che è stata contrassegnata dal [/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) supporta l'opzione del compilatore Address Space Layout Randomization (ASLR) a entropia elevata.</span><span class="sxs-lookup"><span data-stu-id="325ab-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="325ab-104">Syntax</span></span>  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="325ab-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="325ab-105">Arguments</span></span>  
 <span data-ttu-id="325ab-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="325ab-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="325ab-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="325ab-107">Optional.</span></span> <span data-ttu-id="325ab-108">L'opzione è disattivata per impostazione predefinita o se si specifica `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="325ab-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="325ab-109">L'opzione è abilitata se si specifica `-highentropyva` o `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="325ab-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325ab-110">Note</span><span class="sxs-lookup"><span data-stu-id="325ab-110">Remarks</span></span>  
 <span data-ttu-id="325ab-111">Se si specifica questa opzione, le versioni compatibili del kernel di Windows consente un grado più elevato di entropia quando il kernel genera casualmente il layout dello spazio degli indirizzi di un processo come parte di ASLR.</span><span class="sxs-lookup"><span data-stu-id="325ab-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="325ab-112">Se il kernel utilizza un grado più elevato di entropia, un numero maggiore di indirizzi può essere allocato alle aree di memoria quali stack e heap.</span><span class="sxs-lookup"><span data-stu-id="325ab-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="325ab-113">Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="325ab-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="325ab-114">Quando l'opzione è on, l'eseguibile di destinazione e tutti i moduli in cui esso dipende deve essere in grado di gestire i valori dei puntatori sono maggiori di 4 gigabyte (GB) quando i moduli vengono eseguiti come processi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="325ab-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325ab-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="325ab-115">See Also</span></span>  
 [<span data-ttu-id="325ab-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="325ab-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="325ab-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="325ab-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
