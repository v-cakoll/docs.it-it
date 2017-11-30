---
title: -target:winexe (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e155c64689f34c89443c7ff0a3dee38d6c190fcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="targetwinexe-c-compiler-options"></a><span data-ttu-id="51346-102">/target:winexe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="51346-102">/target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="51346-103">L'opzione **/target: winexe** indica al compilatore di creare un file eseguibile (con estensione EXE), il programma di Windows.</span><span class="sxs-lookup"><span data-stu-id="51346-103">The **/target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51346-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51346-104">Syntax</span></span>  
  
```console  
/target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="51346-105">Note</span><span class="sxs-lookup"><span data-stu-id="51346-105">Remarks</span></span>  
 <span data-ttu-id="51346-106">Il file eseguibile verrà creato con estensione .exe.</span><span class="sxs-lookup"><span data-stu-id="51346-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="51346-107">È un programma di Windows che fornisce un'interfaccia utente dalla libreria di .NET Framework o con le API Win32.</span><span class="sxs-lookup"><span data-stu-id="51346-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Win32 APIs.</span></span>  
  
 <span data-ttu-id="51346-108">Usare [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) per creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="51346-108">Use [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="51346-109">A meno che diversamente specificato con l'opzione [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="51346-109">Unless otherwise specified with the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="51346-110">Quando specificato nella riga di comando, tutti i file fino alla successiva opzione **/out** o [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) vengono usati per creare il programma Windows.</span><span class="sxs-lookup"><span data-stu-id="51346-110">When specified at the command line, all files until the next **/out** or [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="51346-111">Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="51346-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="51346-112">L'opzione [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="51346-112">The [/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="51346-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="51346-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="51346-114">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="51346-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="51346-115">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="51346-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="51346-116">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="51346-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="51346-117">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="51346-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51346-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="51346-118">Example</span></span>  
 <span data-ttu-id="51346-119">Compilare `in.cs` in un programma di Windows:</span><span class="sxs-lookup"><span data-stu-id="51346-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc /target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="51346-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51346-120">See Also</span></span>  
 [<span data-ttu-id="51346-121">/target (opzioni del compilatore c#)</span><span class="sxs-lookup"><span data-stu-id="51346-121">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="51346-122">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="51346-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
