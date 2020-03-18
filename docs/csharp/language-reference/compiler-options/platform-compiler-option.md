---
title: -platform (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /platform
helpviewer_keywords:
- platform compiler option [C#]
- -platform compiler option [C#]
- /platform compiler option [C#]
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
ms.openlocfilehash: 5150e871d75c3c34dab10f10cdac3d8322d7a834
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70849874"
---
# <a name="-platform-c-compiler-options"></a><span data-ttu-id="95094-102">-platform (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="95094-102">-platform (C# Compiler Options)</span></span>

<span data-ttu-id="95094-103">Specifica la versione di Common Language Runtime (CLR) in grado di eseguire l'assembly.</span><span class="sxs-lookup"><span data-stu-id="95094-103">Specifies which version of the Common Language Runtime (CLR) can run the assembly.</span></span>

## <a name="syntax"></a><span data-ttu-id="95094-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95094-104">Syntax</span></span>

```console
-platform:string
```

## <a name="parameters"></a><span data-ttu-id="95094-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95094-105">Parameters</span></span>

`string` \
<span data-ttu-id="95094-106">anycpu (impostazione predefinita), anycpu32bitpreferred, ARM, x64, x86 o Itanium.</span><span class="sxs-lookup"><span data-stu-id="95094-106">anycpu (default), anycpu32bitpreferred, ARM, x64, x86, or Itanium.</span></span>

## <a name="remarks"></a><span data-ttu-id="95094-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="95094-107">Remarks</span></span>

- <span data-ttu-id="95094-108">**anycpu** (valore predefinito) consente di compilare l'assembly in modo da poter essere eseguito su qualsiasi piattaforma.</span><span class="sxs-lookup"><span data-stu-id="95094-108">**anycpu** (default) compiles your assembly to run on any platform.</span></span> <span data-ttu-id="95094-109">L'applicazione viene eseguita come processo a 64 bit, quando possibile, e tramite essa viene eseguito il fallback a 32 bit solo quando questa modalità è disponibile.</span><span class="sxs-lookup"><span data-stu-id="95094-109">Your application runs as a 64-bit process whenever possible and falls back to 32-bit when only that mode is available.</span></span>

- <span data-ttu-id="95094-110">**anycpu32bitpreferred** consente di compilare l'assembly in modo da poter essere eseguito su qualsiasi piattaforma.</span><span class="sxs-lookup"><span data-stu-id="95094-110">**anycpu32bitpreferred** compiles your assembly to run on any platform.</span></span> <span data-ttu-id="95094-111">L'applicazione viene eseguita in modalità a 32 bit nei sistemi che supportano sia le applicazioni a 64 bit sia quelle a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="95094-111">Your application runs in 32-bit mode on systems that support both 64-bit and 32-bit applications.</span></span> <span data-ttu-id="95094-112">È possibile specificare questa opzione solo per i progetti destinati a .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="95094-112">You can specify this option only for projects that target the .NET Framework 4.5.</span></span>

- <span data-ttu-id="95094-113">**ARM** compila l'assembly in modo da poter essere eseguito su un computer con processore Advanced RISC Machine (ARM).</span><span class="sxs-lookup"><span data-stu-id="95094-113">**ARM** compiles your assembly to run on a computer that has an Advanced RISC Machine (ARM) processor.</span></span>

- <span data-ttu-id="95094-114">**ARM64** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer con un processore Advanced RISC Machine (ARM) che supporta il set di istruzioni A64.</span><span class="sxs-lookup"><span data-stu-id="95094-114">**ARM64** compiles your assembly to run by the 64-bit CLR on a computer that has an Advanced RISC Machine (ARM) processor that supports the A64 instruction set.</span></span>

- <span data-ttu-id="95094-115">**x64** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer che supporta il set di istruzioni AMD64 o EM64T.</span><span class="sxs-lookup"><span data-stu-id="95094-115">**x64** compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>

- <span data-ttu-id="95094-116">**x86** compila l'assembly in modo che possa essere eseguito da CLR a 32 bit, compatibile con x86.</span><span class="sxs-lookup"><span data-stu-id="95094-116">**x86** compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>

- <span data-ttu-id="95094-117">**Itanium** compila l'assembly in modo che possa essere eseguito da CLR a 64 bit in un computer dotato di processore Itanium.</span><span class="sxs-lookup"><span data-stu-id="95094-117">**Itanium** compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>

<span data-ttu-id="95094-118">In un sistema operativo Windows a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="95094-118">On a 64-bit Windows operating system:</span></span>

- <span data-ttu-id="95094-119">Gli assembly compilati con **-platform:x86** vengono eseguiti dalla versione di Common Language Runtime a 32 bit in WOW64.</span><span class="sxs-lookup"><span data-stu-id="95094-119">Assemblies compiled with **-platform:x86** execute on the 32-bit CLR running under WOW64.</span></span>

- <span data-ttu-id="95094-120">Una DLL compilata con l'opzione **-platform:anycpu** viene eseguita dallo stesso Common Language Runtime del processo in cui viene caricata.</span><span class="sxs-lookup"><span data-stu-id="95094-120">A DLL compiled with the **-platform:anycpu** executes on the same CLR as the process into which it is loaded.</span></span>

- <span data-ttu-id="95094-121">Gli eseguibili compilati con **-platform:anycpu** vengono eseguiti dalla versione di Common Language Runtime a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="95094-121">Executables that are compiled with the **-platform:anycpu** execute on the 64-bit CLR.</span></span>

- <span data-ttu-id="95094-122">Gli eseguibili compilati con l'opzione **-platform:anycpu32bitpreferred** vengono eseguiti dalla versione di Common Language Runtime a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="95094-122">Executables compiled with **-platform:anycpu32bitpreferred** execute on the 32-bit CLR.</span></span>

<span data-ttu-id="95094-123">L'impostazione **anycpu32bitpreferred** è valida solo per file eseguibili (con estensione exe) e richiede .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="95094-123">The **anycpu32bitpreferred** setting is valid only for executable (.EXE) files, and it requires the .NET Framework 4.5.</span></span>

<span data-ttu-id="95094-124">Per altre informazioni sullo sviluppo di un'applicazione da eseguire su un sistema operativo Windows a 64 bit, vedere [Applicazioni a 64 bit](../../../framework/64-bit-apps.md).</span><span class="sxs-lookup"><span data-stu-id="95094-124">For more information about developing an application to run on a Windows 64-bit operating system, see [64-bit Applications](../../../framework/64-bit-apps.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="95094-125">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95094-125">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="95094-126">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="95094-126">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="95094-127">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="95094-127">Click the **Build** property page.</span></span>

3. <span data-ttu-id="95094-128">Modificare la proprietà **Piattaforma di destinazione** e, per i progetti destinati a .NET Framework 4.5, selezionare o deselezionare la casella di controllo **Preferisci 32 bit**.</span><span class="sxs-lookup"><span data-stu-id="95094-128">Modify the **Platform target** property and, for projects that target the .NET Framework 4.5, select or clear the **Prefer 32-bit** check box.</span></span>

> [!NOTE]
> <span data-ttu-id="95094-129">`-platform`non è disponibile nell'ambiente di sviluppo in Visual C.</span><span class="sxs-lookup"><span data-stu-id="95094-129">`-platform` is not available in the development environment in Visual C# Express.</span></span>

<span data-ttu-id="95094-130">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span><span class="sxs-lookup"><span data-stu-id="95094-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.</span></span>

## <a name="example"></a><span data-ttu-id="95094-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="95094-131">Example</span></span>

<span data-ttu-id="95094-132">L'esempio seguente illustra come usare l'opzione **-platform** per specificare che l'applicazione deve essere eseguita dalla versione di Common Language Runtime a 64 bit in un sistema operativo Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="95094-132">The following example shows how to use the **-platform** option to specify that the application should be run by the 64-bit CLR on a 64-bit Windows operating system.</span></span>

```console
csc -platform:anycpu filename.cs
```

## <a name="see-also"></a><span data-ttu-id="95094-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95094-133">See also</span></span>

- [<span data-ttu-id="95094-134">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="95094-134">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="95094-135">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="95094-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
