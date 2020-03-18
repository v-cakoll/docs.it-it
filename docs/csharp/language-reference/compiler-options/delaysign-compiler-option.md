---
title: -delaysign (opzioni del compilatore C#)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970437"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="72506-102">-delaysign (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="72506-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="72506-103">Questa opzione indica al compilatore di riservare spazio nel file di output in modo che si possa aggiungere una firma digitale in un secondo tempo.</span><span class="sxs-lookup"><span data-stu-id="72506-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="72506-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72506-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="72506-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="72506-105">Arguments</span></span>

<span data-ttu-id="72506-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="72506-106">`+` &#124; `-`</span></span>

<span data-ttu-id="72506-107">Usare **-delaysign-** se si vuole un assembly con firma completa.</span><span class="sxs-lookup"><span data-stu-id="72506-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="72506-108">Usare **-delaysign+** se si vuole solo inserire la chiave pubblica nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72506-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="72506-109">L'impostazione predefinita è **-delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="72506-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="72506-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="72506-110">Remarks</span></span>

<span data-ttu-id="72506-111">L'opzione **-delaysign** non ha alcun effetto se non utilizzata con [-keyfile](./keyfile-compiler-option.md) o [-keycontainer](./keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="72506-111">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="72506-112">Le opzioni **-delaysign** e **-publicsign** si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="72506-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="72506-113">Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="72506-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="72506-114">Tale operazione crea una firma digitale archiviata nel file contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="72506-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="72506-115">Quando per un assembly è impostata la firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta successivamente.</span><span class="sxs-lookup"><span data-stu-id="72506-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="72506-116">Ad esempio, l'uso di **-delaysign+** consente a un tester di inserire l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="72506-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="72506-117">Al termine del test, è possibile firmare completamente l'assembly inserendo la chiave privata nell'assembly con l'utilità [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="72506-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="72506-118">Per altre informazioni, vedere [Creazione e uso degli assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) e [Ritardo della firma di un assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="72506-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="72506-119">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="72506-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="72506-120">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="72506-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="72506-121">Modificare la proprietà **Solo firma ritardata**.</span><span class="sxs-lookup"><span data-stu-id="72506-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="72506-122">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="72506-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="72506-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72506-123">See also</span></span>

- [<span data-ttu-id="72506-124">Opzione -publicsign C#</span><span class="sxs-lookup"><span data-stu-id="72506-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="72506-125">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="72506-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="72506-126">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="72506-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
