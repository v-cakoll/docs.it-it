---
title: -target:winexe (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 981f1b0b6ca9f708bb022a3662ab181a4f472040
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606383"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="01a06-102">-target:winexe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="01a06-102">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="01a06-103">Con l'opzione **-target:winexe** il compilatore crea un file eseguibile (EXE), ovvero un programma di Windows.</span><span class="sxs-lookup"><span data-stu-id="01a06-103">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01a06-104">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="01a06-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="01a06-105">Remarks</span></span>  
 <span data-ttu-id="01a06-106">Il file eseguibile verrà creato con estensione .exe.</span><span class="sxs-lookup"><span data-stu-id="01a06-106">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="01a06-107">È un programma di Windows che genera un'interfaccia utente dalla libreria di .NET Framework o con le API Windows.</span><span class="sxs-lookup"><span data-stu-id="01a06-107">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="01a06-108">Usare [-target:exe](./target-exe-compiler-option.md) per creare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="01a06-108">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="01a06-109">Se non diversamente specificato con l'opzione [-out](./out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="01a06-109">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="01a06-110">Se specificato alla riga di comando, tutti i file fino alla successiva opzione **-out** o [-target](./target-compiler-option.md) vengono usati per creare il programma Windows.</span><span class="sxs-lookup"><span data-stu-id="01a06-110">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="01a06-111">Un solo metodo **Main** è necessario nei file del codice sorgente che vengono compilati in un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="01a06-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="01a06-112">L'opzione [-main](./main-compiler-option.md) consente di specificare la classe che contiene il metodo **Main**, nei casi in cui il codice ha più di una classe con un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="01a06-112">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="01a06-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="01a06-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="01a06-114">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="01a06-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="01a06-115">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="01a06-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="01a06-116">Modificare la proprietà **Tipo di output**.</span><span class="sxs-lookup"><span data-stu-id="01a06-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="01a06-117">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="01a06-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01a06-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="01a06-118">Example</span></span>  
 <span data-ttu-id="01a06-119">Compilare `in.cs` in un programma di Windows:</span><span class="sxs-lookup"><span data-stu-id="01a06-119">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="01a06-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01a06-120">See also</span></span>

- [<span data-ttu-id="01a06-121">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="01a06-121">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="01a06-122">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="01a06-122">C# Compiler Options</span></span>](./index.md)
