---
title: -target:appcontainerexe (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 64661e72f9efe190606cadd93558678cb849e8cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74204529"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="73102-102">-target:appcontainerexe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="73102-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="73102-103">Se si usa l'opzione del compilatore **-target:appcontainerexe**, il compilatore crea un file eseguibile Windows (con estensione exe) che deve essere eseguito in un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="73102-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="73102-104">Questa opzione è equivalente a [-target:winexe,](./target-winexe-compiler-option.md) ma è progettata per le app di Windows 8.x Store.</span><span class="sxs-lookup"><span data-stu-id="73102-104">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73102-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73102-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="73102-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="73102-106">Remarks</span></span>  
 <span data-ttu-id="73102-107">Per richiedere che l'app venga eseguita in un contenitore di app, questa opzione imposta un bit nel file [eseguibile di tipo PE](/windows/desktop/Debug/pe-format).</span><span class="sxs-lookup"><span data-stu-id="73102-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="73102-108">Quando questo bit è impostato, viene generato un errore se il metodo CreateProcess tenta di avviare il file eseguibile all'esterno di un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="73102-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="73102-109">A meno che non si usi l'opzione [-out](./out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="73102-109">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="73102-110">Quando si specifica questa opzione al prompt dei comandi, tutti i file fino alla successiva opzione **-out** o **-target** vengono usati per creare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="73102-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="73102-111">Per impostare l'opzione del compilatore nell'IDE</span><span class="sxs-lookup"><span data-stu-id="73102-111">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="73102-112">In **Esplora soluzioni**aprire il menu di scelta rapida per il progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="73102-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="73102-113">Nell'elenco **Tipo di output** della scheda **Applicazione** scegliere **Applicazione Windows Store**.</span><span class="sxs-lookup"><span data-stu-id="73102-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="73102-114">Questa opzione è disponibile solo per i modelli di app di Windows 8.x Store.</span><span class="sxs-lookup"><span data-stu-id="73102-114">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="73102-115">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="73102-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73102-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="73102-116">Example</span></span>  
 <span data-ttu-id="73102-117">Il seguente comando consente di compilare `filename.cs` in un file eseguibile di Windows che può essere eseguito solo in un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="73102-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="73102-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73102-118">See also</span></span>

- [<span data-ttu-id="73102-119">-target (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="73102-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="73102-120">-target:winexe (opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="73102-120">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="73102-121">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="73102-121">C# Compiler Options</span></span>](./index.md)
