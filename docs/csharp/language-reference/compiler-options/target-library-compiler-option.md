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
ms.openlocfilehash: 0bdf8d95004ca11e3d6b9b27568f7310a802a28b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542444"
---
# <a name="-targetlibrary-c-compiler-options"></a><span data-ttu-id="4f4ec-102">-target:library (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="4f4ec-102">-target:library (C# Compiler Options)</span></span>
<span data-ttu-id="4f4ec-103">L'opzione **-target:library** consente la creazione da parte del compilatore di una libreria di collegamento dinamico (DLL), anziché di un file eseguibile (EXE).</span><span class="sxs-lookup"><span data-stu-id="4f4ec-103">The **-target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f4ec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f4ec-104">Syntax</span></span>  
  
```console  
-target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f4ec-105">Note</span><span class="sxs-lookup"><span data-stu-id="4f4ec-105">Remarks</span></span>  
 <span data-ttu-id="4f4ec-106">La libreria creata avrà estensione DLL.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="4f4ec-107">Se non diversamente specificato tramite l'opzione [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-107">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="4f4ec-108">Quando specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o **-target:module** vengono usati per creare il file con estensione dll.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-108">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="4f4ec-109">Quando si compila un file con estensione dll, non è richiesto alcun metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f4ec-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4f4ec-110">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4f4ec-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="4f4ec-111">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="4f4ec-112">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="4f4ec-113">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="4f4ec-114">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f4ec-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4ec-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f4ec-115">Example</span></span>  
 <span data-ttu-id="4f4ec-116">Compilare in `in.cs` creando in `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="4f4ec-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc -target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f4ec-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f4ec-117">See also</span></span>

- [<span data-ttu-id="4f4ec-118">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="4f4ec-118">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="4f4ec-119">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="4f4ec-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
