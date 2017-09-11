---
title: -target:library (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
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
ms.openlocfilehash: c54599a3badf65fe6d53f74f71fde58772afa6c2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="targetlibrary-c-compiler-options"></a><span data-ttu-id="097e6-102">/target:library (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="097e6-102">/target:library (C# Compiler Options)</span></span>
<span data-ttu-id="097e6-103">L'opzione **/target:library** consente la creazione di una libreria DLL, anziché di un file eseguibile EXE.</span><span class="sxs-lookup"><span data-stu-id="097e6-103">The **/target:library** option causes the compiler to create a dynamic-link library (DLL) rather than an executable file (EXE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="097e6-104">Syntax</span></span>  
  
```console  
/target:library  
```  
  
## <a name="remarks"></a><span data-ttu-id="097e6-105">Note</span><span class="sxs-lookup"><span data-stu-id="097e6-105">Remarks</span></span>  
 <span data-ttu-id="097e6-106">La libreria creata avrà estensione DLL.</span><span class="sxs-lookup"><span data-stu-id="097e6-106">The DLL will be created with the .dll extension.</span></span>  
  
 <span data-ttu-id="097e6-107">Se non diversamente specificato mediante l'opzione [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del primo file di input.</span><span class="sxs-lookup"><span data-stu-id="097e6-107">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the first input file.</span></span>  
  
 <span data-ttu-id="097e6-108">Quando specificato alla riga di comando, tutti i file fino alla successiva opzione **/out** o **/target:module** vengono usati per creare il file con estensione dll.</span><span class="sxs-lookup"><span data-stu-id="097e6-108">When specified at the command line, all files up to the next **/out** or **/target:module** option are used to create the .dll file.</span></span>  
  
 <span data-ttu-id="097e6-109">Quando si compila un file con estensione dll, non è richiesto alcun metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="097e6-109">When building a .dll file, a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method is not required.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="097e6-110">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="097e6-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="097e6-111">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="097e6-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="097e6-112">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="097e6-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="097e6-113">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="097e6-113">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="097e6-114">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="097e6-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="097e6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="097e6-115">Example</span></span>  
 <span data-ttu-id="097e6-116">Compilare in `in.cs` creando in `in.dll`:</span><span class="sxs-lookup"><span data-stu-id="097e6-116">Compile `in.cs`, creating `in.dll`:</span></span>  
  
```console  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="097e6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="097e6-117">See Also</span></span>  
 <span data-ttu-id="097e6-118">[-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="097e6-118">[/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md) </span></span>  
 [<span data-ttu-id="097e6-119">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="097e6-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

