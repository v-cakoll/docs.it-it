---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408699"
---
# <a name="-delaysign"></a><span data-ttu-id="a5465-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="a5465-102">-delaysign</span></span>

<span data-ttu-id="a5465-103">Specifica se l'assembly avrà firma completa o parziale.</span><span class="sxs-lookup"><span data-stu-id="a5465-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5465-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5465-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="a5465-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a5465-105">Arguments</span></span>

<span data-ttu-id="a5465-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a5465-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="a5465-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a5465-107">Optional.</span></span> <span data-ttu-id="a5465-108">Utilizzare `-delaysign-` se si desidera che l'assembly abbia firma completa.</span><span class="sxs-lookup"><span data-stu-id="a5465-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="a5465-109">Usare `-delaysign+` se si vuole inserire la chiave pubblica nell'assembly e lo spazio riservato per l'hash firmato.</span><span class="sxs-lookup"><span data-stu-id="a5465-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="a5465-110">Il valore predefinito è `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="a5465-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5465-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="a5465-111">Remarks</span></span>

<span data-ttu-id="a5465-112">L' `-delaysign` opzione non ha alcun effetto a meno che non venga usata con [-](keyfile.md) [filecontainer o-filecontainer](keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="a5465-112">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="a5465-113">Quando si richiede un assembly con firma completa, il compilatore genera un hash per il file contenente il manifesto (i metadati dell'assembly) e firma tale hash con la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="a5465-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="a5465-114">La firma digitale risultante viene archiviata nel file contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="a5465-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="a5465-115">Quando un assembly ha una firma ritardata, il compilatore non calcola e archivia la firma, ma riserva spazio nel file in modo che la firma possa essere aggiunta in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a5465-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="a5465-116">Usando, ad esempio `-delaysign+` , uno sviluppatore di un'organizzazione può distribuire le versioni di test senza segno di un assembly che i tester possono registrare con il global assembly cache e usare.</span><span class="sxs-lookup"><span data-stu-id="a5465-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="a5465-117">Al termine dell'operazione sull'assembly, la persona responsabile della chiave privata dell'organizzazione può firmare completamente l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a5465-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="a5465-118">Questo compartimentazione protegge la chiave privata dell'organizzazione dalla divulgazione, consentendo a tutti gli sviluppatori di lavorare sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="a5465-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="a5465-119">Per ulteriori informazioni sulla firma di un assembly [, vedere Creazione e utilizzo di assembly con nome sicuro](../../../standard/assembly/create-use-strong-named.md) .</span><span class="sxs-lookup"><span data-stu-id="a5465-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="a5465-120">Per impostare-delaysign in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="a5465-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="a5465-121">Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a5465-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a5465-122">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a5465-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="a5465-123">Fare clic sulla scheda **Firma** .</span><span class="sxs-lookup"><span data-stu-id="a5465-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="a5465-124">Impostare il valore nella casella **solo firma ritardata** .</span><span class="sxs-lookup"><span data-stu-id="a5465-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5465-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5465-125">See also</span></span>

- [<span data-ttu-id="a5465-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a5465-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a5465-127">-filefile</span><span class="sxs-lookup"><span data-stu-id="a5465-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="a5465-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="a5465-128">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="a5465-129">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="a5465-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
