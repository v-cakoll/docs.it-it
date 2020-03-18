---
title: -target:library (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
ms.openlocfilehash: c947b2015c19d0809cab4535e989ee83ebf17fd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606389"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="f9307-102">-target:library (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f9307-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="f9307-103">L'opzione **-target:library** consente la creazione da parte del compilatore di una libreria di collegamento dinamico (DLL), anziché di un file eseguibile (EXE).</span><span class="sxs-lookup"><span data-stu-id="f9307-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9307-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9307-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="f9307-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f9307-105">Remarks</span></span>  
 <span data-ttu-id="f9307-106">La libreria creata avrà estensione DLL.</span><span class="sxs-lookup"><span data-stu-id="f9307-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="f9307-107">Se non diversamente specificato tramite l'opzione [-out](./out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="f9307-107">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="f9307-108">Quando specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o **-target:module** vengono usati per creare il file con estensione dll.</span><span class="sxs-lookup"><span data-stu-id="f9307-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="f9307-109">Quando si compila un file con estensione dll, non è richiesto alcun metodo [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9307-109">When building a .dll file, a [Main](../../programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f9307-110">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9307-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f9307-111">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="f9307-111">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f9307-112">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="f9307-112">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="f9307-113">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="f9307-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="f9307-114">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9307-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9307-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9307-115">Example</span></span>  
 <span data-ttu-id="f9307-116">Compilare in `in.cs` creando in `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="f9307-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9307-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9307-117">See also</span></span>

- [<span data-ttu-id="f9307-118">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f9307-118">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="f9307-119">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="f9307-119">C# Compiler Options</span></span>](./index.md)
