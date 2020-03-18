---
title: -optimize (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: bec99ca582070a99fd8b734ef8a7b9e71d945488
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606607"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="6edad-102">-optimize (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6edad-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="6edad-103">L'opzione **-optimize** abilita o disabilita le ottimizzazioni eseguite dal compilatore per ridurre le dimensioni del file di output e aumentarne la velocità e l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="6edad-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6edad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6edad-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="6edad-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6edad-105">Remarks</span></span>  
 <span data-ttu-id="6edad-106">**-optimize** comunica poi a Common Language Runtime di ottimizzare il codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6edad-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="6edad-107">Per impostazione predefinita, le ottimizzazioni sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="6edad-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="6edad-108">Per abilitarle, specificare **-optimize+**.</span><span class="sxs-lookup"><span data-stu-id="6edad-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="6edad-109">Durante la compilazione di un modulo per l'uso da parte di un assembly, specificare per **-optimize** le stesse impostazioni usate per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6edad-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="6edad-110">**-o** è la versione abbreviata di **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="6edad-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="6edad-111">Le opzioni **-optimize** e [-debug](./debug-compiler-option.md) possono essere usate in modo combinato.</span><span class="sxs-lookup"><span data-stu-id="6edad-111">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6edad-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6edad-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6edad-113">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="6edad-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="6edad-114">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="6edad-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="6edad-115">Modificare la proprietà **Ottimizza codice**.</span><span class="sxs-lookup"><span data-stu-id="6edad-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="6edad-116">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="6edad-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6edad-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="6edad-117">Example</span></span>  
 <span data-ttu-id="6edad-118">Compilare `t2.cs` e abilitare le ottimizzazioni del compilatore:</span><span class="sxs-lookup"><span data-stu-id="6edad-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="6edad-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6edad-119">See also</span></span>

- [<span data-ttu-id="6edad-120">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="6edad-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6edad-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6edad-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
