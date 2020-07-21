---
title: -target (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: 80cec001b27000e71b74f380a0f33e30602c01af
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86473909"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="3b3b5-102">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="3b3b5-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="3b3b5-103">L'opzione del compilatore **-target** può essere specificata in uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b3b5-103">The **-target** compiler option can be specified in one of the following forms:</span></span>  
  
 [<span data-ttu-id="3b3b5-104">-target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="3b3b5-104">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="3b3b5-105">Per creare un file con estensione exe per le app di Windows 8. x Store.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-105">To create an .exe file for Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="3b3b5-106">-target:exe</span><span class="sxs-lookup"><span data-stu-id="3b3b5-106">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="3b3b5-107">Per creare un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="3b3b5-108">-target:library</span><span class="sxs-lookup"><span data-stu-id="3b3b5-108">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="3b3b5-109">Per creare una libreria di codice.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="3b3b5-110">-target:module</span><span class="sxs-lookup"><span data-stu-id="3b3b5-110">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="3b3b5-111">Per creare un modulo.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-111">To create a module.</span></span>  
  
 [<span data-ttu-id="3b3b5-112">-target:winexe</span><span class="sxs-lookup"><span data-stu-id="3b3b5-112">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="3b3b5-113">Per creare un programma di Windows.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="3b3b5-114">-target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="3b3b5-114">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="3b3b5-115">Per creare un file con estensione winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="3b3b5-116">A meno che non si specifichi **-target: module**, **-target** causa la posizione di un manifesto dell'assembly .NET Framework in un file di output.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="3b3b5-117">Per altre informazioni, vedere [assembly in .NET](../../../standard/assembly/index.md) e [attributi comuni](../attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="3b3b5-117">For more information, see [Assemblies in .NET](../../../standard/assembly/index.md) and [Common Attributes](../attributes/global.md).</span></span>  
  
 <span data-ttu-id="3b3b5-118">Il manifesto dell'assembly viene inserito nel primo file di output con estensione .exe della compilazione o nel primo DLL, se non esiste alcun file di output .exe.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="3b3b5-119">Ad esempio, nella riga di comando seguente il manifesto verrà inserito in `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="3b3b5-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="3b3b5-120">Il compilatore crea solo un manifesto dell'assembly per ogni compilazione.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="3b3b5-121">Le informazioni su tutti i file in una compilazione vengono inserite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="3b3b5-122">Tutti i file di output tranne quelli creati con **-target: module** possono contenere un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="3b3b5-123">Quando si generano più file di output nella riga di comando, è possibile creare solo un manifesto e deve essere inseriti nel primo file di output specificato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="3b3b5-124">Indipendentemente da quale sia il primo file di output (**-target:exe**, **-target:winexe**, **-target:library** o **-target:module**), tutti gli altri file di output generati nella stessa compilazione devono essere moduli (**-target:module**).</span><span class="sxs-lookup"><span data-stu-id="3b3b5-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="3b3b5-125">Se si crea un assembly, è possibile indicare che tutto o parte del codice è conforme a CLS con l'attributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="3b3b5-126">Per altre informazioni sull'impostazione di questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b3b5-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b3b5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b3b5-127">See also</span></span>

- [<span data-ttu-id="3b3b5-128">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="3b3b5-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3b3b5-129">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="3b3b5-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="3b3b5-130">-subsystemversion (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="3b3b5-130">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
