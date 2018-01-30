---
title: -delaysign (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a931dccb2aebd2c898b55f0a007d9fac8da42f2e
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2018
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="89905-102">-delaysign (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="89905-102">-delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="89905-103">Questa opzione indica al compilatore di riservare spazio nel file di output in modo che si possa aggiungere una firma digitale in un secondo tempo.</span><span class="sxs-lookup"><span data-stu-id="89905-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89905-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89905-104">Syntax</span></span>  
  
```console  
-delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="89905-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="89905-105">Arguments</span></span>  
 <span data-ttu-id="89905-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="89905-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="89905-107">Usare **-delaysign-** se si vuole un assembly con firma completa.</span><span class="sxs-lookup"><span data-stu-id="89905-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="89905-108">Usare **-delaysign+** se si vuole solo inserire la chiave pubblica nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="89905-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="89905-109">L'impostazione predefinita è **-delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="89905-109">The default is **-delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89905-110">Note</span><span class="sxs-lookup"><span data-stu-id="89905-110">Remarks</span></span>  
 <span data-ttu-id="89905-111">L'opzione **-delaysign** ha effetto solo se abbinata all'opzione [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) o [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="89905-111">The **-delaysign** option has no effect unless used with [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [-keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="89905-112">Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="89905-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="89905-113">La firma digitale risultante viene archiviata nel file contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="89905-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="89905-114">Quando per un assembly è impostata la firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta successivamente.</span><span class="sxs-lookup"><span data-stu-id="89905-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="89905-115">Ad esempio, l'uso di **-delaysign+** consente a un tester di inserire l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="89905-115">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="89905-116">Al termine del test, è possibile firmare completamente l'assembly inserendo la chiave privata nell'assembly con l'utilità [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="89905-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>  
  
 <span data-ttu-id="89905-117">Per altre informazioni, vedere [Creazione e utilizzo degli assembly con nome sicuro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) e [Ritardo della firma di un assembly](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="89905-117">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="89905-118">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89905-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="89905-119">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="89905-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="89905-120">Modificare la proprietà **Solo firma ritardata**.</span><span class="sxs-lookup"><span data-stu-id="89905-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="89905-121">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="89905-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89905-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89905-122">See Also</span></span>  
 [<span data-ttu-id="89905-123">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="89905-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="89905-124">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="89905-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
