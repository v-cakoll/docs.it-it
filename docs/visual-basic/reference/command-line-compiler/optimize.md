---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397441"
---
# <a name="-optimize"></a><span data-ttu-id="0b88f-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="0b88f-102">-optimize</span></span>
<span data-ttu-id="0b88f-103">Abilita o Disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b88f-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b88f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b88f-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b88f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0b88f-105">Arguments</span></span>  
  
|<span data-ttu-id="0b88f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="0b88f-106">Term</span></span>|<span data-ttu-id="0b88f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="0b88f-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0b88f-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0b88f-108">`+` &#124; `-`</span></span>|<span data-ttu-id="0b88f-109">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0b88f-109">Optional.</span></span> <span data-ttu-id="0b88f-110">L' `-optimize-` opzione Disabilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b88f-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="0b88f-111">L' `-optimize+` opzione consente le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0b88f-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="0b88f-112">Per impostazione predefinita, le ottimizzazioni sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="0b88f-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b88f-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="0b88f-113">Remarks</span></span>  
 <span data-ttu-id="0b88f-114">Le ottimizzazioni del compilatore consentono di ridurre le dimensioni del file di output rendendolo più veloce ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="0b88f-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="0b88f-115">Tuttavia, poiché le ottimizzazioni generano una riorganizzazione del codice nel file di output, `-optimize+` può rendere difficile il debug.</span><span class="sxs-lookup"><span data-stu-id="0b88f-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="0b88f-116">Tutti i moduli generati con `-target:module` per un assembly devono usare le stesse `-optimize` impostazioni dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0b88f-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="0b88f-117">Per ulteriori informazioni, vedere [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="0b88f-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="0b88f-118">È possibile combinare le `-optimize` `-debug` Opzioni e.</span><span class="sxs-lookup"><span data-stu-id="0b88f-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="0b88f-119">Per impostare-optimize in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="0b88f-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0b88f-120">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="0b88f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0b88f-121">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="0b88f-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="0b88f-122">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="0b88f-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0b88f-123">3. fare clic sul pulsante **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="0b88f-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="0b88f-124">4. modificare la casella di controllo **Abilita ottimizzazioni** .</span><span class="sxs-lookup"><span data-stu-id="0b88f-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b88f-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b88f-125">Example</span></span>  
 <span data-ttu-id="0b88f-126">Il codice seguente compila `T2.vb` e Abilita le ottimizzazioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b88f-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b88f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b88f-127">See also</span></span>

- [<span data-ttu-id="0b88f-128">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b88f-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0b88f-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b88f-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="0b88f-130">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="0b88f-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="0b88f-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b88f-131">-target (Visual Basic)</span></span>](target.md)
