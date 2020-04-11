---
title: 'Procedura: creare wrapper COM'
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
ms.openlocfilehash: 035d6439ec90426d7b68e05043ea8b6722f81d28
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121593"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="a21a4-102">Procedura: creare wrapper COM</span><span class="sxs-lookup"><span data-stu-id="a21a4-102">How to: Create COM Wrappers</span></span>

<span data-ttu-id="a21a4-103">È possibile creare wrapper COM (Component Object Model) usando le funzionalità di Visual Studio 2005 o gli strumenti .NET Framework Tlbimp.exe e Regasm.exe.</span><span class="sxs-lookup"><span data-stu-id="a21a4-103">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="a21a4-104">Entrambi i metodi generano due tipi di wrapper COM:</span><span class="sxs-lookup"><span data-stu-id="a21a4-104">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="a21a4-105">Oggetto [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) da una libreria dei tipi per l'esecuzione di un oggetto COM nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="a21a4-105">A [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="a21a4-106">Oggetto [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) con le impostazioni del Registro di sistema richieste per l'esecuzione di un oggetto gestito in un'applicazione nativa.</span><span class="sxs-lookup"><span data-stu-id="a21a4-106">A [COM Callable Wrapper](../../standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="a21a4-107">In Visual Studio 2005 è possibile aggiungere il wrapper COM come riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="a21a4-107">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="a21a4-108">Eseguire il wrapping di oggetti COM in un'applicazione gestita</span><span class="sxs-lookup"><span data-stu-id="a21a4-108">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="a21a4-109">Per creare un Runtime Callable Wrapper con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a21a4-109">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="a21a4-110">Aprire il progetto per l'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="a21a4-110">Open the project for your managed application.</span></span>

2. <span data-ttu-id="a21a4-111">Scegliere **Mostra tutti i file** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-111">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="a21a4-112">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-112">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="a21a4-113">Nella finestra di dialogo Aggiungi riferimento fare clic sulla scheda **COM**, selezionare il componente che si vuole usare e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="a21a4-114">In **Esplora soluzioni** si noti che il componente COM viene aggiunto alla cartella Riferimenti nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a21a4-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="a21a4-115">È ora possibile scrivere codice per accedere all'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="a21a4-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="a21a4-116">È possibile iniziare dichiarando l'oggetto, ad esempio con un'istruzione `Imports` per Visual Basic o con un'istruzione `Using` per C#.</span><span class="sxs-lookup"><span data-stu-id="a21a4-116">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="a21a4-117">Se si desidera programmare i componenti di Microsoft Office, installare [innanzitutto Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508).</span><span class="sxs-lookup"><span data-stu-id="a21a4-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies Redistributable](https://www.microsoft.com/Download/details.aspx?id=3508).</span></span>
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="a21a4-118">Per creare un Runtime Callable Wrapper con gli strumenti di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a21a4-118">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="a21a4-119">Eseguire lo strumento [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="a21a4-119">Run the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="a21a4-120">Questo strumento crea un assembly che contiene i metadati di runtime per i tipi definiti nella libreria dei tipi originale.</span><span class="sxs-lookup"><span data-stu-id="a21a4-120">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="a21a4-121">Eseguire il wrapping di oggetti gestiti in un'applicazione nativa</span><span class="sxs-lookup"><span data-stu-id="a21a4-121">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="a21a4-122">Per creare un COM Callable Wrapper con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a21a4-122">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="a21a4-123">Creare un progetto libreria di classi per la classe gestita che si vuole eseguire in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="a21a4-123">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="a21a4-124">La classe deve avere un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="a21a4-124">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="a21a4-125">Verificare che l'assembly nel file AssemblyInfo abbia un numero di versione in quattro parti completo.</span><span class="sxs-lookup"><span data-stu-id="a21a4-125">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="a21a4-126">Questo numero è obbligatorio per la gestione del controllo delle versioni nel Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="a21a4-126">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="a21a4-127">Per altre informazioni sui numeri di versione, vedere [Controllo delle versioni degli assembly](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="a21a4-127">For more information about version numbers, see [Assembly Versioning](../../standard/assembly/versioning.md).</span></span>  
  
2. <span data-ttu-id="a21a4-128">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-128">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="a21a4-129">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-129">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="a21a4-130">Selezionare la casella di controllo **Registra per interoperabilità COM**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-130">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="a21a4-131">Quando si compila il progetto, l'assembly viene automaticamente registrato per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="a21a4-131">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="a21a4-132">Se si compila un'applicazione nativa in Visual Studio 2005, è possibile usare l'assembly scegliendo **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a21a4-132">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="a21a4-133">Per creare un COM Callable Wrapper con gli strumenti di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a21a4-133">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="a21a4-134">Eseguire lo strumento [Regasm.exe (strumento di registrazione di assembly)](../tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a21a4-134">Run the [Regasm.exe (Assembly Registration Tool)](../tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="a21a4-135">Questo strumento legge i metadati in un assembly e aggiunge le voci necessarie nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a21a4-135">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="a21a4-136">Di conseguenza, i client COM possono creare classi di .NET Framework in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="a21a4-136">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="a21a4-137">È possibile usare l'assembly come se fosse una classe COM nativa.</span><span class="sxs-lookup"><span data-stu-id="a21a4-137">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="a21a4-138">È possibile eseguire Regasm.exe su un assembly disponibile in qualsiasi directory e quindi eseguire [Gacutil.exe (strumento Global Assembly Cache)](../tools/gacutil-exe-gac-tool.md) per spostarlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a21a4-138">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="a21a4-139">Lo spostamento dell'assembly non invalida le voci del Registro di sistema per la posizione, perché la Global Assembly Cache viene sempre esaminata se l'assembly non viene trovato in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="a21a4-139">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21a4-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a21a4-140">See also</span></span>

- [<span data-ttu-id="a21a4-141">Runtime Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="a21a4-141">Runtime Callable Wrapper</span></span>](../../standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="a21a4-142">COM Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="a21a4-142">COM Callable Wrapper</span></span>](../../standard/native-interop/com-callable-wrapper.md)
