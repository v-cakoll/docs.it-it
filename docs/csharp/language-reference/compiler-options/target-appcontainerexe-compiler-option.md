---
title: -target:appcontainerexe (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9ab407f14483bbb5abaf3dc23b0cf204091b74ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="cb00c-102">/target:appcontainerexe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="cb00c-102">/target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="cb00c-103">Se si usa l'opzione del compilatore **/target:appcontainerexe**, il compilatore crea un file eseguibile di Windows (exe) che deve essere eseguito in un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="cb00c-103">If you use the **/target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="cb00c-104">Questa opzione equivale a [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), ma è progettata per le app [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb00c-104">This option is equivalent to [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) but is designed for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb00c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb00c-105">Syntax</span></span>  
  
```console  
/target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb00c-106">Note</span><span class="sxs-lookup"><span data-stu-id="cb00c-106">Remarks</span></span>  
 <span data-ttu-id="cb00c-107">Per richiedere che l'app venga eseguita in un contenitore di app, questa opzione imposta un bit nel file [eseguibile di tipo PE](http://go.microsoft.com/fwlink/p/?LinkId=236960).</span><span class="sxs-lookup"><span data-stu-id="cb00c-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](http://go.microsoft.com/fwlink/p/?LinkId=236960) (PE) file.</span></span> <span data-ttu-id="cb00c-108">Quando questo bit è impostato, viene generato un errore se il metodo CreateProcess tenta di avviare il file eseguibile all'esterno di un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="cb00c-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="cb00c-109">A meno che non si usi l'opzione [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), il nome del file di output corrisponderà al nome del file di input contenente il metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="cb00c-109">Unless you use the [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="cb00c-110">Quando si specifica questa opzione da un prompt dei comandi, tutti i file fino alla successiva opzione **/out** o **/target** vengono usati per creare il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="cb00c-110">When you specify this option at a command prompt, all files until the next **/out** or **/target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="cb00c-111">Per impostare l'opzione del compilatore nell'IDE</span><span class="sxs-lookup"><span data-stu-id="cb00c-111">To set this compiler option in the IDE</span></span>  
  
1.  <span data-ttu-id="cb00c-112">In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cb00c-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="cb00c-113">Nell'elenco **Tipo di output** della scheda **Applicazione** scegliere **Applicazione Windows Store**.</span><span class="sxs-lookup"><span data-stu-id="cb00c-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="cb00c-114">Questa opzione è disponibile solo per i modelli di app [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb00c-114">This option is available only for [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] app templates.</span></span>  
  
 <span data-ttu-id="cb00c-115">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb00c-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb00c-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb00c-116">Example</span></span>  
 <span data-ttu-id="cb00c-117">Il seguente comando consente di compilare `filename.cs` in un file eseguibile di Windows che può essere eseguito solo in un contenitore di app.</span><span class="sxs-lookup"><span data-stu-id="cb00c-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc /target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb00c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb00c-118">See Also</span></span>  
 [<span data-ttu-id="cb00c-119">/target (opzioni del compilatore c#)</span><span class="sxs-lookup"><span data-stu-id="cb00c-119">/target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="cb00c-120">/target: winexe (opzioni del compilatore c#)</span><span class="sxs-lookup"><span data-stu-id="cb00c-120">/target:winexe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [<span data-ttu-id="cb00c-121">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="cb00c-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
