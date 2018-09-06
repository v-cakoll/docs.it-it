---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 479f9f639548eb81351d1df3f8f08b29b393cba1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890883"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="f4a4e-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="f4a4e-102">-moduleassemblyname</span></span>
<span data-ttu-id="f4a4e-103">Specifica il nome dell'assembly di cui fa parte il modulo.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4a4e-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4a4e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f4a4e-105">Arguments</span></span>  
  
|<span data-ttu-id="f4a4e-106">Termine</span><span class="sxs-lookup"><span data-stu-id="f4a4e-106">Term</span></span>|<span data-ttu-id="f4a4e-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4a4e-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="f4a4e-108">Il nome dell'assembly che questo modulo farà parte di.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4a4e-109">Note</span><span class="sxs-lookup"><span data-stu-id="f4a4e-109">Remarks</span></span>  
 <span data-ttu-id="f4a4e-110">Il compilatore elabora il `-moduleassemblyname` solo se opzione il `-target:module` opzione è stata specificata.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="f4a4e-111">Ciò indica al compilatore di creare un modulo.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="f4a4e-112">Il modulo è stato creato dal compilatore è valido solo per l'assembly specificato con il `-moduleassemblyname` opzione.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="f4a4e-113">Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="f4a4e-114">Il `-moduleassemblyname` opzione è necessaria solo quando vengono soddisfatte le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4a4e-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="f4a4e-115">Un tipo di dati del modulo deve avere accesso a un `Friend` tipo in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="f4a4e-116">L'assembly di riferimento ha concesso l'accesso assembly friend all'assembly in cui verrà compilato il modulo.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="f4a4e-117">Per altre informazioni sulla creazione di un modulo, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="f4a4e-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="f4a4e-118">Per altre informazioni sugli assembly friend, vedere [assembly Friend](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="f4a4e-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4a4e-119">Il `-moduleassemblyname` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo quando esegue la compilazione da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f4a4e-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a4e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a4e-120">See Also</span></span>  
 [<span data-ttu-id="f4a4e-121">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="f4a4e-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="f4a4e-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f4a4e-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f4a4e-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4a4e-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="f4a4e-124">-main</span><span class="sxs-lookup"><span data-stu-id="f4a4e-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="f4a4e-125">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4a4e-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="f4a4e-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="f4a4e-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="f4a4e-127">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="f4a4e-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="f4a4e-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f4a4e-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="f4a4e-129">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="f4a4e-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
