---
title: 'Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 1f6176746b783d020c809fb0b5d55d741ce0148b
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245475"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="18663-102">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18663-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="18663-103">Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione.</span><span class="sxs-lookup"><span data-stu-id="18663-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="18663-104">Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria gestita senza dover essere ricompilato per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="18663-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="18663-105">L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="18663-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="18663-106">L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi.</span><span class="sxs-lookup"><span data-stu-id="18663-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="18663-107">Tuttavia, è anche possibile usare l'incorporamento dei tipi con una soluzione completamente gestita.</span><span class="sxs-lookup"><span data-stu-id="18663-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="18663-108">Le informazioni sul tipo possono essere incorporate da un assembly con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="18663-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="18663-109">L'assembly espone almeno un'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="18663-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="18663-110">Le interfacce incorporate vengono annotate con un attributo `ComImport` e un attributo `Guid` (e un GUID univoco).</span><span class="sxs-lookup"><span data-stu-id="18663-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="18663-111">L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="18663-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="18663-112">(Per impostazione predefinita, i modelli di progetto Visual Basic includono un livello di assembly `Guid` attributo.)</span><span class="sxs-lookup"><span data-stu-id="18663-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="18663-113">Dopo aver specificato le interfacce pubbliche che possono essere incorporate, è possibile creare classi di runtime che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="18663-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="18663-114">Un programma client può quindi incorporare le informazioni sul tipo per tali interfacce in fase di progettazione facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la proprietà `Embed Interop Types` del riferimento su `True`.</span><span class="sxs-lookup"><span data-stu-id="18663-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="18663-115">Ciò equivale a usare il compilatore della riga di comando e fare riferimento all'assembly usando l'opzione del compilatore `/link`.</span><span class="sxs-lookup"><span data-stu-id="18663-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="18663-116">Il programma client può quindi caricare le istanze degli oggetti di runtime tipizzati come tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="18663-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="18663-117">Se si crea una nuova versione dell'assembly di runtime con nome sicuro, il programma client non deve essere ricompilato con l'assembly di runtime aggiornato.</span><span class="sxs-lookup"><span data-stu-id="18663-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="18663-118">Il programma client continua invece a usare qualsiasi versione dell'assembly di runtime disponibile, usando le informazioni sul tipo incorporate per le interfacce pubbliche.</span><span class="sxs-lookup"><span data-stu-id="18663-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="18663-119">Poiché la funzione principale dell'incorporamento dei tipi è supportare l'incorporamento delle informazioni sui tipi dagli assembly di interoperabilità COM, le limitazioni seguenti si applicano quando si incorporano informazioni sul tipo in una soluzione completamente gestita:</span><span class="sxs-lookup"><span data-stu-id="18663-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="18663-120">Vengono incorporati solo gli attributi specifici per l'interoperabilità COM, gli altri attributi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="18663-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="18663-121">Se un tipo usa parametri generici e il tipo del parametro generico è un tipo incorporato, non è possibile usare quel tipo superando un limite di assembly.</span><span class="sxs-lookup"><span data-stu-id="18663-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="18663-122">Esempi di superamento di un limite di assembly sono chiamare un metodo da un altro assembly o derivare un tipo da un tipo definito in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="18663-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="18663-123">Le costanti non vengono incorporate.</span><span class="sxs-lookup"><span data-stu-id="18663-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="18663-124">La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="18663-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="18663-125">È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="18663-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="18663-126">In questa procedura dettagliata, si eseguiranno le operazioni:</span><span class="sxs-lookup"><span data-stu-id="18663-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="18663-127">Creare un assembly con nome sicuro che ha un'interfaccia pubblica che contiene informazioni sul tipo che possono essere incorporate.</span><span class="sxs-lookup"><span data-stu-id="18663-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="18663-128">Creare un assembly di runtime con nome sicuro che implementa tale interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="18663-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="18663-129">Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="18663-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="18663-130">Modificare e ricompilare l'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="18663-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="18663-131">Eseguire il programma client per verificare se la nuova versione dell'assembly di runtime viene usata senza dover ricompilare il programma client.</span><span class="sxs-lookup"><span data-stu-id="18663-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="18663-132">Creare un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="18663-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="18663-133">Per creare il progetto di interfaccia di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="18663-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="18663-134">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="18663-135">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="18663-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="18663-136">Selezionare **Libreria di classi** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="18663-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="18663-137">Nella casella **Nome** digitare `TypeEquivalenceInterface` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="18663-138">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="18663-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="18663-139">Nelle **Esplora soluzioni**, fare doppio clic su file Class1.vb e fare clic su **rinominare**.</span><span class="sxs-lookup"><span data-stu-id="18663-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="18663-140">Rinominare il file `ISampleInterface.vb` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="18663-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="18663-141">Modificando il nome del file, anche la classe verrà rinominata `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="18663-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="18663-142">Questa classe rappresenterà l'interfaccia pubblica per la classe.</span><span class="sxs-lookup"><span data-stu-id="18663-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="18663-143">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18663-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="18663-144">Fare clic sulla scheda **Compila**. Impostare il percorso di output su un percorso valido nel computer di sviluppo, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="18663-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="18663-145">Questo percorso verrà usato anche in un passaggio successivo di questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="18663-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="18663-146">Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**.</span><span class="sxs-lookup"><span data-stu-id="18663-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="18663-147">Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**.</span><span class="sxs-lookup"><span data-stu-id="18663-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="18663-148">Nella casella **Nome file di chiave** digitare `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="18663-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="18663-149">Deselezionare la casella di controllo **Proteggi file di chiave con una password**.</span><span class="sxs-lookup"><span data-stu-id="18663-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="18663-150">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="18663-151">Aprire il file vb.</span><span class="sxs-lookup"><span data-stu-id="18663-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="18663-152">Aggiungere il codice seguente al file della classe ISampleInterface per creare l'interfaccia ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="18663-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```vb  
    Imports System.Runtime.InteropServices  
  
    <ComImport()>  
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>  
    Public Interface ISampleInterface  
        Sub GetUserInput()  
        ReadOnly Property UserInput As String  
    End Interface  
    ```  
  
7.  <span data-ttu-id="18663-153">Scegliere **Crea GUID** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="18663-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="18663-154">Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="18663-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="18663-155">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="18663-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="18663-156">Nell'attributo `Guid` eliminare il GUID di esempio e incollare il GUID copiato dalla finestra di dialogo **Crea GUID**.</span><span class="sxs-lookup"><span data-stu-id="18663-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="18663-157">Rimuovere le parentesi graffe ({}) dal GUID copiato.</span><span class="sxs-lookup"><span data-stu-id="18663-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="18663-158">Scegliere **Mostra tutti i file** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-158">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="18663-159">Nelle **Esplora soluzioni**, espandere il **My Project** cartella.</span><span class="sxs-lookup"><span data-stu-id="18663-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="18663-160">Fare doppio clic il file AssemblyInfo. vb.</span><span class="sxs-lookup"><span data-stu-id="18663-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="18663-161">Aggiungere il seguente attributo al file.</span><span class="sxs-lookup"><span data-stu-id="18663-161">Add the following attribute to the file.</span></span>  
  
    ```vb  
    <Assembly: ImportedFromTypeLib("")>  
    ```  
  
     <span data-ttu-id="18663-162">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="18663-162">Save the file.</span></span>  
  
11. <span data-ttu-id="18663-163">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="18663-163">Save the project.</span></span>  
  
12. <span data-ttu-id="18663-164">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="18663-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="18663-165">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="18663-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="18663-166">Creare una classe di runtime</span><span class="sxs-lookup"><span data-stu-id="18663-166">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="18663-167">Per creare il progetto di runtime di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="18663-167">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="18663-168">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="18663-169">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="18663-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="18663-170">Selezionare **Libreria di classi** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="18663-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="18663-171">Nella casella **Nome** digitare `TypeEquivalenceRuntime` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="18663-172">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="18663-172">The new project is created.</span></span>  
  
3.  <span data-ttu-id="18663-173">Nelle **Esplora soluzioni**, fare doppio clic su file Class1.vb e fare clic su **rinominare**.</span><span class="sxs-lookup"><span data-stu-id="18663-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="18663-174">Rinominare il file `SampleClass.vb` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="18663-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="18663-175">Modificando il nome del file, anche la classe verrà rinominata `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="18663-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="18663-176">Questa classe implementerà l'interfaccia `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="18663-176">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="18663-177">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18663-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="18663-178">Fare clic sulla scheda **Compila**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="18663-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="18663-179">Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**.</span><span class="sxs-lookup"><span data-stu-id="18663-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="18663-180">Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**.</span><span class="sxs-lookup"><span data-stu-id="18663-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="18663-181">Nella casella **Nome file di chiave** digitare `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="18663-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="18663-182">Deselezionare la casella di controllo **Proteggi file di chiave con una password**.</span><span class="sxs-lookup"><span data-stu-id="18663-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="18663-183">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-183">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="18663-184">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="18663-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="18663-185">Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output.</span><span class="sxs-lookup"><span data-stu-id="18663-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="18663-186">Selezionare il file TypeEquivalenceInterface.dll e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="18663-187">Scegliere **Mostra tutti i file** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-187">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="18663-188">In **Esplora soluzioni** espandere la cartella **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="18663-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="18663-189">Selezionare il riferimento TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="18663-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="18663-190">Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Versione specifica** su **False**.</span><span class="sxs-lookup"><span data-stu-id="18663-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="18663-191">Aggiungere il codice seguente al file della classe SampleClass per creare la classe SampleClass.</span><span class="sxs-lookup"><span data-stu-id="18663-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
  
    Public Class SampleClass  
        Implements ISampleInterface  
  
        Private p_UserInput As String  
        Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput  
            Get  
                Return p_UserInput  
            End Get  
        End Property  
  
        Public Sub GetUserInput() Implements ISampleInterface.GetUserInput  
            Console.WriteLine("Please enter a value:")  
            p_UserInput = Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
10. <span data-ttu-id="18663-192">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="18663-192">Save the project.</span></span>  
  
11. <span data-ttu-id="18663-193">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="18663-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="18663-194">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="18663-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="18663-195">Creare un progetto client</span><span class="sxs-lookup"><span data-stu-id="18663-195">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="18663-196">Per creare il progetto client di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="18663-196">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="18663-197">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="18663-198">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="18663-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="18663-199">Selezionare **Applicazione console** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="18663-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="18663-200">Nella casella **Nome** digitare `TypeEquivalenceClient` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="18663-201">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="18663-201">The new project is created.</span></span>  
  
3.  <span data-ttu-id="18663-202">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18663-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="18663-203">Fare clic sulla scheda **Compila**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="18663-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="18663-204">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="18663-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="18663-205">Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output.</span><span class="sxs-lookup"><span data-stu-id="18663-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="18663-206">Selezionare il file TypeEquivalenceInterface.dll (non TypeEquivalenceRuntime.dll) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18663-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="18663-207">Scegliere **Mostra tutti i file** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="18663-207">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="18663-208">In **Esplora soluzioni** espandere la cartella **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="18663-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="18663-209">Selezionare il riferimento TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="18663-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="18663-210">Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Incorpora tipi di interoperabilità** su **True**.</span><span class="sxs-lookup"><span data-stu-id="18663-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="18663-211">Aggiungere il codice seguente nel file Module1.vb per creare il programma client.</span><span class="sxs-lookup"><span data-stu-id="18663-211">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
    ```vb  
    Imports TypeEquivalenceInterface  
    Imports System.Reflection  
  
    Module Module1  
  
        Sub Main()  
            Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")  
            Dim sampleClass As ISampleInterface = CType( _  
                sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)  
            sampleClass.GetUserInput()  
            Console.WriteLine(sampleClass.UserInput)  
            Console.WriteLine(sampleAssembly.GetName().Version)  
            Console.ReadLine()  
        End Sub  
  
    End Module  
    ```  
  
8.  <span data-ttu-id="18663-212">Premere CTRL+F5 per compilare ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="18663-212">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="18663-213">Modificare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="18663-213">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="18663-214">Per modificare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="18663-214">To modify the interface</span></span>  
  
1.  <span data-ttu-id="18663-215">In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="18663-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="18663-216">Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18663-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="18663-217">Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="18663-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="18663-218">Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="18663-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="18663-219">Aprire il file vb.</span><span class="sxs-lookup"><span data-stu-id="18663-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="18663-220">Aggiungere la riga di codice seguente all'interfaccia ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="18663-220">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```vb  
    Function GetDate() As Date  
    ```  
  
     <span data-ttu-id="18663-221">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="18663-221">Save the file.</span></span>  
  
4.  <span data-ttu-id="18663-222">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="18663-222">Save the project.</span></span>  
  
5.  <span data-ttu-id="18663-223">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="18663-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="18663-224">Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="18663-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="18663-225">Modificare la classe di runtime</span><span class="sxs-lookup"><span data-stu-id="18663-225">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="18663-226">Per modificare la classe di runtime</span><span class="sxs-lookup"><span data-stu-id="18663-226">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="18663-227">In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="18663-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="18663-228">Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18663-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="18663-229">Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="18663-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="18663-230">Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="18663-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="18663-231">Aprire il SampleClass.vbfile.</span><span class="sxs-lookup"><span data-stu-id="18663-231">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="18663-232">Aggiungere le seguenti righe di codice alla classe SampleClass.</span><span class="sxs-lookup"><span data-stu-id="18663-232">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="18663-233">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="18663-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="18663-234">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="18663-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="18663-235">Una versione aggiornata del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato in precedenza, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="18663-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="18663-236">In Esplora File aprire la cartella del percorso di output, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="18663-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="18663-237">Fare doppio clic su TypeEquivalenceClient.exe per eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="18663-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="18663-238">Il programma rifletterà la nuova versione dell'assembly TypeEquivalenceRuntime senza dover essere ricompilato.</span><span class="sxs-lookup"><span data-stu-id="18663-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18663-239">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18663-239">See Also</span></span>  
 [<span data-ttu-id="18663-240">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18663-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="18663-241">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="18663-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="18663-242">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="18663-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="18663-243">Assembly e Global Assembly Cache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18663-243">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
