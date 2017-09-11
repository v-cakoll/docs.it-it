---
title: -target:module (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:module
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
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
ms.openlocfilehash: 23c91fe0e4002ebf4c002eb4e0c7e25020fed356
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="targetmodule-c-compiler-options"></a><span data-ttu-id="bf7f6-102">/target:module (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="bf7f6-102">/target:module (C# Compiler Options)</span></span>
<span data-ttu-id="bf7f6-103">Questa opzione indica al compilatore di non generare un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf7f6-104">Syntax</span></span>  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf7f6-105">Note</span><span class="sxs-lookup"><span data-stu-id="bf7f6-105">Remarks</span></span>  
 <span data-ttu-id="bf7f6-106">Per impostazione predefinita, l'estensione del file di output creato eseguendo la compilazione con questa opzione sarà netmodule.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="bf7f6-107">Un file che non dispone di un manifesto dell'assembly non può essere caricato da Common Language Runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="bf7f6-108">È tuttavia possibile incorporare un file di questo tipo nel manifesto dell'assembly di un assembly tramite [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f6-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="bf7f6-109">Se viene creato più di un modulo in un'unica compilazione, i tipi [internal](../../../csharp/language-reference/keywords/internal.md) in un modulo saranno disponibili per gli altri moduli nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="bf7f6-110">Quando il codice in un modulo fa riferimento a tipi `internal` in un altro modulo, sarà necessario incorporare entrambi i moduli in un manifesto dell'assembly tramite **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **/addmodule**.</span></span>  
  
 <span data-ttu-id="bf7f6-111">La creazione di un modulo non è supportata nell'ambiente di sviluppo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="bf7f6-112">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf7f6-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf7f6-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf7f6-113">Example</span></span>  
 <span data-ttu-id="bf7f6-114">Compilare in `in.cs` creando in `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="bf7f6-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf7f6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf7f6-115">See Also</span></span>  
 <span data-ttu-id="bf7f6-116">[-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="bf7f6-116">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="bf7f6-117">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="bf7f6-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

