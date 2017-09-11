---
title: -target (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target
dev_langs:
- CSharp
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 22dc86ce0c0a24681d05e54e5f1ba4f36295659a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="target-c-compiler-options"></a><span data-ttu-id="eff3a-102">/target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="eff3a-102">/target (C# Compiler Options)</span></span>
<span data-ttu-id="eff3a-103">L'opzione del compilatore **/target** può essere specificata in uno dei quattro moduli seguenti:</span><span class="sxs-lookup"><span data-stu-id="eff3a-103">The **/target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="eff3a-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="eff3a-104">/target:appcontainerexe</span></span>](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="eff3a-105">Per creare un file con estensione exe per le applicazioni [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eff3a-105">To create an .exe file for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="eff3a-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="eff3a-106">/target:exe</span></span>](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 <span data-ttu-id="eff3a-107">Per creare un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="eff3a-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="eff3a-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="eff3a-108">/target:library</span></span>](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 <span data-ttu-id="eff3a-109">Per creare una libreria di codice.</span><span class="sxs-lookup"><span data-stu-id="eff3a-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="eff3a-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="eff3a-110">/target:module</span></span>](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 <span data-ttu-id="eff3a-111">Per creare un modulo.</span><span class="sxs-lookup"><span data-stu-id="eff3a-111">To create a module.</span></span>  
  
 [<span data-ttu-id="eff3a-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="eff3a-112">/target:winexe</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 <span data-ttu-id="eff3a-113">Per creare un programma di Windows.</span><span class="sxs-lookup"><span data-stu-id="eff3a-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="eff3a-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="eff3a-114">/target:winmdobj</span></span>](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 <span data-ttu-id="eff3a-115">Per creare un file con estensione winmdobj intermedio.</span><span class="sxs-lookup"><span data-stu-id="eff3a-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="eff3a-116">Se non si specifica **/target: module**, **/target** provoca l'inserimento di un manifesto dell'assembly di .NET Framework in un file di output.</span><span class="sxs-lookup"><span data-stu-id="eff3a-116">Unless you specify **/target:module**, **/target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="eff3a-117">Per altre informazioni, vedere [Assembly in Common Language Runtime](https://msdn.microsoft.com/library/k3677y81) e [Attributi comuni](http://msdn.microsoft.com/library/2f48a7ec-9683-4899-a1d2-a08be8fc558b).</span><span class="sxs-lookup"><span data-stu-id="eff3a-117">For more information, see [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81) and [Common Attributes](http://msdn.microsoft.com/library/2f48a7ec-9683-4899-a1d2-a08be8fc558b).</span></span>  
  
 <span data-ttu-id="eff3a-118">Il manifesto dell'assembly viene inserito nel primo file di output con estensione .exe della compilazione o nel primo DLL, se non esiste alcun file di output .exe.</span><span class="sxs-lookup"><span data-stu-id="eff3a-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="eff3a-119">Ad esempio, nella riga di comando seguente il manifesto verrà inserito in `1.exe`:</span><span class="sxs-lookup"><span data-stu-id="eff3a-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="eff3a-120">Il compilatore crea solo un manifesto dell'assembly per ogni compilazione.</span><span class="sxs-lookup"><span data-stu-id="eff3a-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="eff3a-121">Le informazioni su tutti i file in una compilazione vengono inserite nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="eff3a-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="eff3a-122">Tutti i file di output, ad eccezione di quelli creati con **/target:module** possono contenere un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="eff3a-122">All output files except those created with **/target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="eff3a-123">Quando si generano più file di output nella riga di comando, è possibile creare solo un manifesto e deve essere inseriti nel primo file di output specificato nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="eff3a-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="eff3a-124">Indipendentemente da quale sia il primo file di output (**/target:exe**, **/target:winexe**, **/target:library** o **/target:module**), tutti gli altri file di output generati nella stessa compilazione devono essere moduli (**/target:module**).</span><span class="sxs-lookup"><span data-stu-id="eff3a-124">No matter what the first output file is (**/target:exe**, **/target:winexe**, **/target:library** or **/target:module**), any other output files produced in the same compilation must be modules (**/target:module**).</span></span>  
  
 <span data-ttu-id="eff3a-125">Se si crea un assembly, è possibile indicare che tutto o parte del codice è conforme a CLS con l'attributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="eff3a-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="eff3a-126">Per altre informazioni sull'impostazione di questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="eff3a-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff3a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eff3a-127">See Also</span></span>  
 <span data-ttu-id="eff3a-128">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="eff3a-128">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="eff3a-129">[Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="eff3a-129">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 [<span data-ttu-id="eff3a-130">-subsystemversion (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="eff3a-130">/subsystemversion (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)

