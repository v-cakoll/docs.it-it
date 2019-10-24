---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775652"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="653d8-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="653d8-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="653d8-103">Indica se un eseguibile a 64 bit o un eseguibile contrassegnato dall'opzione del compilatore [-Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) supporta la sequenza casuale del layout dello spazio degli indirizzi a entropia elevata (ASLR).</span><span class="sxs-lookup"><span data-stu-id="653d8-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="653d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="653d8-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="653d8-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="653d8-105">Arguments</span></span>  
 <span data-ttu-id="653d8-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="653d8-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="653d8-107">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="653d8-107">Optional.</span></span> <span data-ttu-id="653d8-108">Per impostazione predefinita, l'opzione è disattivata oppure se si specifica `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="653d8-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="653d8-109">L'opzione è attiva se si specifica `-highentropyva` o `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="653d8-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="653d8-110">Note</span><span class="sxs-lookup"><span data-stu-id="653d8-110">Remarks</span></span>  
 <span data-ttu-id="653d8-111">Se si specifica questa opzione, le versioni compatibili del kernel di Windows possono usare livelli di entropia più elevati quando il kernel esegue in modo casuale il layout dello spazio degli indirizzi di un processo come parte di ASLR.</span><span class="sxs-lookup"><span data-stu-id="653d8-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="653d8-112">Se il kernel usa livelli di entropia più elevati, è possibile allocare un numero maggiore di indirizzi alle aree di memoria quali stack e heap.</span><span class="sxs-lookup"><span data-stu-id="653d8-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="653d8-113">Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="653d8-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="653d8-114">Quando l'opzione è impostata su on, l'eseguibile di destinazione e tutti i moduli da cui dipende devono essere in grado di gestire valori di puntatore maggiori di 4 gigabyte (GB) quando tali moduli sono in esecuzione come processi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="653d8-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="653d8-115">See also</span></span>

- [<span data-ttu-id="653d8-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="653d8-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="653d8-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="653d8-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
