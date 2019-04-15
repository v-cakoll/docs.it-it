---
title: -lib (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /lib
helpviewer_keywords:
- lib compiler option [C#]
- -lib compiler option [C#]
- /lib compiler option [C#]
ms.assetid: b0efcc88-e8aa-4df4-a00b-8bdef70b7673
ms.openlocfilehash: 49920a46f1d970c3f00025c3dc3eb384c937aa99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319404"
---
# <a name="-lib-c-compiler-options"></a><span data-ttu-id="63d40-102">-lib (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="63d40-102">-lib (C# Compiler Options)</span></span>
<span data-ttu-id="63d40-103">L'opzione **-lib** specifica la posizione degli assembly a cui si fa riferimento tramite l'opzione [-reference (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="63d40-103">The **-lib** option specifies the location of assemblies referenced by means of the [-reference (C# Compiler Options)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63d40-104">Syntax</span></span>  
  
```console  
-lib:dir1[,dir2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="63d40-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="63d40-105">Arguments</span></span>  
 `dir1`  
 <span data-ttu-id="63d40-106">Directory in cui il compilatore può effettuare la ricerca se un assembly cui viene fatto riferimento non si trova nella cartella di lavoro corrente (quella da cui si chiama il compilatore) o nella directory di sistema di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="63d40-106">A directory for the compiler to look in if a referenced assembly is not found in the current working directory (the directory from which you are invoking the compiler) or in the common language runtime's system directory.</span></span>  
  
 `dir2`  
 <span data-ttu-id="63d40-107">Una o più directory aggiuntive in cui effettuare la ricerca dei riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="63d40-107">One or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="63d40-108">Separare i nomi delle directory aggiuntive con una virgola, senza inserire spazi.</span><span class="sxs-lookup"><span data-stu-id="63d40-108">Separate additional directory names with a comma, and without white space between them.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63d40-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63d40-109">Remarks</span></span>  
 <span data-ttu-id="63d40-110">La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="63d40-110">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="63d40-111">Directory di lavoro corrente,</span><span class="sxs-lookup"><span data-stu-id="63d40-111">Current working directory.</span></span> <span data-ttu-id="63d40-112">ovvero la directory da cui viene chiamato il compilatore.</span><span class="sxs-lookup"><span data-stu-id="63d40-112">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="63d40-113">Directory di sistema di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="63d40-113">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="63d40-114">Directory specificate da **-lib**.</span><span class="sxs-lookup"><span data-stu-id="63d40-114">Directories specified by **-lib**.</span></span>  
  
4. <span data-ttu-id="63d40-115">Directory specificate dalla variabile di ambiente LIB.</span><span class="sxs-lookup"><span data-stu-id="63d40-115">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="63d40-116">Per specificare un riferimento a un assembly, usare **-reference**.</span><span class="sxs-lookup"><span data-stu-id="63d40-116">Use **-reference** to specify an assembly reference.</span></span>  
  
 <span data-ttu-id="63d40-117">L'opzione **-lib** è di tipo additivo: se viene specificata più volte, ogni nuovo valore verrà aggiunto a eventuali valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="63d40-117">**-lib** is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="63d40-118">In alternativa a **-lib**, è possibile copiare nella directory di lavoro tutti gli assembly necessari. Sarà quindi sufficiente passare a **-reference** il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="63d40-118">An alternative to using **-lib** is to copy into the working directory any required assemblies; this will allow you to simply pass the assembly name to **-reference**.</span></span> <span data-ttu-id="63d40-119">In seguito sarà possibile eliminare gli assembly dalla directory di lavoro.</span><span class="sxs-lookup"><span data-stu-id="63d40-119">You can then delete the assemblies from the working directory.</span></span> <span data-ttu-id="63d40-120">Dal momento che il percorso dell'assembly dipendente non è specificato nel manifesto dell'assembly, sarà possibile avviare l'applicazione sul computer di destinazione perché trovi e usi l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="63d40-120">Since the path to the dependent assembly is not specified in the assembly manifest, the application can be started on the target computer and will find and use the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="63d40-121">Il fatto che nel compilatore sia possibile fare riferimento all'assembly non implica che Common Language Runtime sarà in grado di trovare e caricare l'assembly in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="63d40-121">Because the compiler can reference the assembly does not imply the common language runtime will be able to find and load the assembly at runtime.</span></span> <span data-ttu-id="63d40-122">Per informazioni dettagliate sulla modalità di ricerca degli assembly a cui viene fatto riferimento in fase di esecuzione, vedere [Come il runtime individua gli assembly](../../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="63d40-122">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="63d40-123">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63d40-123">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="63d40-124">Aprire la finestra di dialogo **Pagine delle proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="63d40-124">Open the project's **Property Pages** dialog box.</span></span>  
  
2. <span data-ttu-id="63d40-125">Fare clic sulla pagina delle proprietà **Percorso riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="63d40-125">Click the **References Path** property page.</span></span>  
  
3. <span data-ttu-id="63d40-126">Modificare il contenuto della casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="63d40-126">Modify the contents of the list box.</span></span>  
  
 <span data-ttu-id="63d40-127">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span><span class="sxs-lookup"><span data-stu-id="63d40-127">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ReferencePath%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63d40-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="63d40-128">Example</span></span>  
 <span data-ttu-id="63d40-129">Compilare t2.cs per creare un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="63d40-129">Compile t2.cs to create an .exe file.</span></span> <span data-ttu-id="63d40-130">Verranno cercati i riferimenti agli assembly nella directory di lavoro e nella directory radice dell'unità C.</span><span class="sxs-lookup"><span data-stu-id="63d40-130">The compiler will look in the working directory and in the root directory of the C drive for assembly references.</span></span>  
  
```console  
csc -lib:c:\ -reference:t2.dll t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="63d40-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63d40-131">See also</span></span>

- [<span data-ttu-id="63d40-132">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="63d40-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="63d40-133">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="63d40-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
