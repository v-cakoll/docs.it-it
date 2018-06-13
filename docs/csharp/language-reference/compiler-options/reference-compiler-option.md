---
title: -reference (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: 4a96da3668a73368dd98055a9082479f162b7b45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218176"
---
# <a name="-reference-c-compiler-options"></a><span data-ttu-id="5c32f-102">-reference (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="5c32f-102">-reference (C# Compiler Options)</span></span>
<span data-ttu-id="5c32f-103">Con l'opzione **-reference** il compilatore importa nel progetto corrente le informazioni sui tipi [public](../../../csharp/language-reference/keywords/public.md) disponibili nel file specificato e consente quindi di fare riferimento ai metadati dai file di assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="5c32f-103">The **-reference** option causes the compiler to import [public](../../../csharp/language-reference/keywords/public.md) type information in the specified file into the current project, thus enabling you to reference metadata from the specified assembly files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c32f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c32f-104">Syntax</span></span>  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c32f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5c32f-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="5c32f-106">Nome di un file contenente il manifesto di un assembly.</span><span class="sxs-lookup"><span data-stu-id="5c32f-106">The name of a file that contains an assembly manifest.</span></span> <span data-ttu-id="5c32f-107">Per importare più file, specificare un'opzione **-reference** per ogni file.</span><span class="sxs-lookup"><span data-stu-id="5c32f-107">To import more than one file, include a separate **-reference** option for each file.</span></span>  
  
 `alias`  
 <span data-ttu-id="5c32f-108">Identificatore C# valido che rappresenta uno spazio dei nomi di primo livello contenente tutti gli spazi dei nomi dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5c32f-108">A valid C# identifier that will represent a root namespace that will contain all namespaces in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c32f-109">Note</span><span class="sxs-lookup"><span data-stu-id="5c32f-109">Remarks</span></span>  
 <span data-ttu-id="5c32f-110">Per importare da più file, includere un'opzione **-reference** per ogni file.</span><span class="sxs-lookup"><span data-stu-id="5c32f-110">To import from more than one file, include a **-reference** option for each file.</span></span>  
  
 <span data-ttu-id="5c32f-111">È necessario che i file importati contengano un manifesto e che il file di output sia stato compilato specificando un'opzione [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) diversa da [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5c32f-111">The files you import must contain a manifest; the output file must have been compiled with one of the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) options other than [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="5c32f-112">**-r** rappresenta la versione abbreviata di **-reference**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-112">**-r** is the short form of **-reference**.</span></span>  
  
 <span data-ttu-id="5c32f-113">Usare [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) per importare metadati da un file di output che non contiene un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5c32f-113">Use [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) to import metadata from an output file that does not contain an assembly manifest.</span></span>  
  
 <span data-ttu-id="5c32f-114">Se si fa riferimento a un assembly (assembly A) che fa a sua volta riferimento a un secondo assembly (assembly B), è necessario fare riferimento all'assembly B nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c32f-114">If you reference an assembly (Assembly A) that references another assembly (Assembly B), you will need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="5c32f-115">Se un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dell'assembly B.</span><span class="sxs-lookup"><span data-stu-id="5c32f-115">A type you use from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="5c32f-116">Se si chiama un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="5c32f-116">You invoke a field, property, event, or method that has a return type or parameter type from Assembly B.</span></span>  
  
 <span data-ttu-id="5c32f-117">Per specificare la directory in cui si trovano uno o più assembly cui si fa riferimento, usare [-lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5c32f-117">Use [-lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md) to specify the directory in which one or more of your assembly references is located.</span></span> <span data-ttu-id="5c32f-118">Nell'argomento dedicato a **-lib** sono indicate anche le directory in cui il compilatore ricerca gli assembly.</span><span class="sxs-lookup"><span data-stu-id="5c32f-118">The **-lib** topic also discusses the directories in which the compiler searches for assemblies.</span></span>  
  
 <span data-ttu-id="5c32f-119">Perché il compilatore sia in grado di riconoscere un tipo in un assembly e non in un modulo, è necessario imporre la risoluzione del tipo stesso. A questo scopo, è possibile definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="5c32f-119">In order for the compiler to recognize a type in an assembly, and not in a module, it needs to be forced to resolve the type, which you can do by defining an instance of the type.</span></span> <span data-ttu-id="5c32f-120">La risoluzione dei nomi dei tipi in un assembly può avvenire anche con altre modalità. Se, ad esempio, si eredita da un tipo in un assembly, il nome del tipo sarà riconosciuto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="5c32f-120">There are other ways to resolve type names in an assembly for the compiler: for example, if you inherit from a type in an assembly, the type name will then be recognized by the compiler.</span></span>  
  
 <span data-ttu-id="5c32f-121">In alcuni casi è necessario fare riferimento a due versioni diverse dello stesso componente da un unico assembly.</span><span class="sxs-lookup"><span data-stu-id="5c32f-121">Sometimes it is necessary to reference two different versions of the same component from within one assembly.</span></span> <span data-ttu-id="5c32f-122">A questo scopo, usare l'opzione di secondo livello alias dell'opzione **-reference** per ogni file, in modo che sia possibile distinguere tra le due versioni.</span><span class="sxs-lookup"><span data-stu-id="5c32f-122">To do this, use the alias suboption on the **-reference** switch for each file to distinguish between the two files.</span></span> <span data-ttu-id="5c32f-123">Questo alias verrà usato come qualificatore per il nome del componente, quindi risolto nel componente stesso in uno dei file.</span><span class="sxs-lookup"><span data-stu-id="5c32f-123">This alias will be used as a qualifier for the component name, and will resolve to the component in one of the files.</span></span>  
  
 <span data-ttu-id="5c32f-124">Per impostazione predefinita, viene usato il file di risposta csc (.rsp), che fa riferimento agli assembly .NET Framework di uso comune.</span><span class="sxs-lookup"><span data-stu-id="5c32f-124">The csc response (.rsp) file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="5c32f-125">Usare [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) se non si vuole che il compilatore usi csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="5c32f-125">Use [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) if you do not want the compiler to use csc.rsp.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c32f-126">In Visual Studio usare la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-126">In Visual Studio, use the **Add Reference** dialog box.</span></span> <span data-ttu-id="5c32f-127">Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere riferimenti mediante Gestione riferimenti](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span><span class="sxs-lookup"><span data-stu-id="5c32f-127">For more information, see [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).</span></span> <span data-ttu-id="5c32f-128">Per garantire un comportamento equivalente tra l'aggiunta di riferimenti usare `-reference` e aggiungere riferimenti tramite la finestra di dialogo **Aggiungi riferimento**, impostando la proprietà **Incorpora tipi di interoperabilità** su **False** per l'assembly che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="5c32f-128">To ensure equivalent behavior between adding references by using `-reference` and adding references by using the **Add Reference** dialog box, set the **Embed Interop Types** property to **False** for the assembly that you're adding.</span></span> <span data-ttu-id="5c32f-129">Per questa proprietà il valore predefinito è **True**.</span><span class="sxs-lookup"><span data-stu-id="5c32f-129">**True** is the default value for the property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c32f-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c32f-130">Example</span></span>  
 <span data-ttu-id="5c32f-131">L'esempio seguente illustra come usare la funzionalità [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="5c32f-131">This example shows how to use the [extern alias](../../../csharp/language-reference/keywords/extern-alias.md) feature.</span></span>  
  
 <span data-ttu-id="5c32f-132">Il file di origine viene compilato e i metadati vengono importati dai file `grid.dll` e `grid20.dll`, compilati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5c32f-132">You compile the source file and import metadata from `grid.dll` and `grid20.dll`,which have been compiled previously.</span></span> <span data-ttu-id="5c32f-133">Nelle due DLL sono presenti versioni distinte dello stesso componente. Usare due opzioni **-reference** con opzioni alias per compilare il file di origine.</span><span class="sxs-lookup"><span data-stu-id="5c32f-133">The two DLLs contain separate versions of the same component, and you use two **-reference** with alias options to compile the source file.</span></span> <span data-ttu-id="5c32f-134">Le opzioni sono analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c32f-134">The options look like this:</span></span>  
  
 <span data-ttu-id="5c32f-135">-reference:GridV1=grid.dll e -reference:GridV2=grid20.dll</span><span class="sxs-lookup"><span data-stu-id="5c32f-135">-reference:GridV1=grid.dll and -reference:GridV2=grid20.dll</span></span>  
  
 <span data-ttu-id="5c32f-136">In questo modo vengono impostati gli alias esterni "GridV1" e "GridV2", da usare nel programma tramite un'istruzione extern:</span><span class="sxs-lookup"><span data-stu-id="5c32f-136">This sets up the external aliases "GridV1" and "GridV2," which you use in your program by means of an extern statement:</span></span>  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 <span data-ttu-id="5c32f-137">Una volta completate queste operazioni, è possibile fare riferimento al controllo griglia dal file grid.dll aggiungendo il prefisso GridV1 al nome del controllo, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5c32f-137">Once this is done, you can refer to the grid control from grid.dll by prefixing the control name with GridV1, like this:</span></span>  
  
```csharp  
GridV1::Grid  
```  
  
 <span data-ttu-id="5c32f-138">È anche possibile fare riferimento al controllo griglia dal file grid20.dll aggiungendo il prefisso GridV2 al nome del controllo, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5c32f-138">In addition, you can refer to the grid control from grid20.dll by prefixing the control name with GridV2 like this:</span></span>  
  
```csharp  
GridV2::Grid   
```  
  
## <a name="see-also"></a><span data-ttu-id="5c32f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c32f-139">See Also</span></span>  
 [<span data-ttu-id="5c32f-140">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="5c32f-140">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="5c32f-141">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="5c32f-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
