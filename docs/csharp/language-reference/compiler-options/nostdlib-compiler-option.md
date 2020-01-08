---
title: -nostdlib (opzioni del compilatore C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: ad8a2b5fc87dd7beee86d96331cf3961315be533
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345082"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="0c37a-102">-nostdlib (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="0c37a-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="0c37a-103">**-nostdlib** impedisce l'importazione di mscorlib.dll, che definisce l'intero spazio dei nomi di sistema.</span><span class="sxs-lookup"><span data-stu-id="0c37a-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c37a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c37a-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="0c37a-105">Note</span><span class="sxs-lookup"><span data-stu-id="0c37a-105">Remarks</span></span>

<span data-ttu-id="0c37a-106">Usare questa opzione se si vuole definire o creare uno spazio dei nomi e oggetti System personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0c37a-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="0c37a-107">Se non si specifica **-nostdlib**, mscorlib.dll viene importata nel programma (equivale a specificare **-nostdlib-** ).</span><span class="sxs-lookup"><span data-stu-id="0c37a-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="0c37a-108">Specificare **-nostdlib** equivale a specificare **-nostdlib+** .</span><span class="sxs-lookup"><span data-stu-id="0c37a-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="0c37a-109">Per impostare questa opzione del compilatore in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c37a-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="0c37a-110">Le istruzioni seguenti si applicano solo a Visual Studio 2015 (e versioni precedenti).</span><span class="sxs-lookup"><span data-stu-id="0c37a-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="0c37a-111">La proprietà di compilazione **mscorlib. dll** non è disponibile nelle versioni più recenti di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c37a-111">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="0c37a-112">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="0c37a-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="0c37a-113">Fare clic sulla pagina di proprietà **Compilazione** .</span><span class="sxs-lookup"><span data-stu-id="0c37a-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="0c37a-114">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="0c37a-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="0c37a-115">Modificare la proprietà **Ometti riferimenti a libreria standard (mscorlib.dll)** .</span><span class="sxs-lookup"><span data-stu-id="0c37a-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="0c37a-116">Per impostare l'opzione del compilatore a livello di codice</span><span class="sxs-lookup"><span data-stu-id="0c37a-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="0c37a-117">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c37a-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c37a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c37a-118">See also</span></span>

- [<span data-ttu-id="0c37a-119">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="0c37a-119">C# Compiler Options</span></span>](./index.md)
