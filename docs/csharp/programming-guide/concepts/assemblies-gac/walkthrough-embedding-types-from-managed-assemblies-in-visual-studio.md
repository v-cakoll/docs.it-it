---
title: 'Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cbd95c71525a92714ab5758855964e323345b2e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="03a87-102">Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="03a87-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="03a87-103">Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione.</span><span class="sxs-lookup"><span data-stu-id="03a87-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="03a87-104">Ovvero, il programma può essere scritto in modo da usare tipi di più versioni di una libreria gestita senza dover essere ricompilato per ogni versione.</span><span class="sxs-lookup"><span data-stu-id="03a87-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="03a87-105">L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="03a87-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="03a87-106">L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi.</span><span class="sxs-lookup"><span data-stu-id="03a87-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="03a87-107">Tuttavia, è anche possibile usare l'incorporamento dei tipi con una soluzione completamente gestita.</span><span class="sxs-lookup"><span data-stu-id="03a87-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="03a87-108">Le informazioni sul tipo possono essere incorporate da un assembly con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="03a87-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="03a87-109">L'assembly espone almeno un'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="03a87-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="03a87-110">Le interfacce incorporate vengono annotate con un attributo `ComImport` e un attributo `Guid` (e un GUID univoco).</span><span class="sxs-lookup"><span data-stu-id="03a87-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="03a87-111">L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="03a87-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="03a87-112">Per impostazione predefinita, i modelli di progetto Visual C# includono un attributo `Guid` a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="03a87-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="03a87-113">Dopo aver specificato le interfacce pubbliche che possono essere incorporate, è possibile creare classi di runtime che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="03a87-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="03a87-114">Un programma client può quindi incorporare le informazioni sul tipo per tali interfacce in fase di progettazione facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la proprietà `Embed Interop Types` del riferimento su `True`.</span><span class="sxs-lookup"><span data-stu-id="03a87-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="03a87-115">Ciò equivale a usare il compilatore della riga di comando e fare riferimento all'assembly usando l'opzione del compilatore `/link`.</span><span class="sxs-lookup"><span data-stu-id="03a87-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="03a87-116">Il programma client può quindi caricare le istanze degli oggetti di runtime tipizzati come tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="03a87-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="03a87-117">Se si crea una nuova versione dell'assembly di runtime con nome sicuro, il programma client non deve essere ricompilato con l'assembly di runtime aggiornato.</span><span class="sxs-lookup"><span data-stu-id="03a87-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="03a87-118">Il programma client continua invece a usare qualsiasi versione dell'assembly di runtime disponibile, usando le informazioni sul tipo incorporate per le interfacce pubbliche.</span><span class="sxs-lookup"><span data-stu-id="03a87-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="03a87-119">Poiché la funzione principale dell'incorporamento dei tipi è supportare l'incorporamento delle informazioni sui tipi dagli assembly di interoperabilità COM, le limitazioni seguenti si applicano quando si incorporano informazioni sul tipo in una soluzione completamente gestita:</span><span class="sxs-lookup"><span data-stu-id="03a87-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="03a87-120">Vengono incorporati solo gli attributi specifici per l'interoperabilità COM, gli altri attributi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="03a87-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="03a87-121">Se un tipo usa parametri generici e il tipo del parametro generico è un tipo incorporato, non è possibile usare quel tipo superando un limite di assembly.</span><span class="sxs-lookup"><span data-stu-id="03a87-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="03a87-122">Esempi di superamento di un limite di assembly sono chiamare un metodo da un altro assembly o derivare un tipo da un tipo definito in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="03a87-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="03a87-123">Le costanti non vengono incorporate.</span><span class="sxs-lookup"><span data-stu-id="03a87-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="03a87-124">La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="03a87-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="03a87-125">È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="03a87-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="03a87-126">In questa procedura dettagliata, si eseguiranno le operazioni:</span><span class="sxs-lookup"><span data-stu-id="03a87-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="03a87-127">Creare un assembly con nome sicuro che ha un'interfaccia pubblica che contiene informazioni sul tipo che possono essere incorporate.</span><span class="sxs-lookup"><span data-stu-id="03a87-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="03a87-128">Creare un assembly di runtime con nome sicuro che implementa tale interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="03a87-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="03a87-129">Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="03a87-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="03a87-130">Modificare e ricompilare l'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="03a87-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="03a87-131">Eseguire il programma client per verificare se la nuova versione dell'assembly di runtime viene usata senza dover ricompilare il programma client.</span><span class="sxs-lookup"><span data-stu-id="03a87-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="03a87-132">Creare un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="03a87-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="03a87-133">Per creare il progetto di interfaccia di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="03a87-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="03a87-134">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="03a87-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="03a87-135">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="03a87-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="03a87-136">Selezionare **Libreria di classi** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="03a87-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="03a87-137">Nella casella **Nome** digitare `TypeEquivalenceInterface` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="03a87-138">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="03a87-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="03a87-139">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file Class1.cs e fare clic su **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="03a87-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="03a87-140">Rinominare il file `ISampleInterface.cs` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="03a87-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="03a87-141">Modificando il nome del file, anche la classe verrà rinominata `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="03a87-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="03a87-142">Questa classe rappresenterà l'interfaccia pubblica per la classe.</span><span class="sxs-lookup"><span data-stu-id="03a87-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="03a87-143">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="03a87-144">Fare clic sulla scheda **Compila**. Impostare il percorso di output su un percorso valido nel computer di sviluppo, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="03a87-144">Click the the **Build** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="03a87-145">Questo percorso verrà usato anche in un passaggio successivo di questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="03a87-145">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="03a87-146">Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**.</span><span class="sxs-lookup"><span data-stu-id="03a87-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="03a87-147">Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**.</span><span class="sxs-lookup"><span data-stu-id="03a87-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="03a87-148">Nella casella **Nome file di chiave** digitare `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="03a87-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="03a87-149">Deselezionare la casella di controllo **Proteggi file di chiave con una password**.</span><span class="sxs-lookup"><span data-stu-id="03a87-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="03a87-150">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="03a87-151">Aprire il file ISampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="03a87-151">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="03a87-152">Aggiungere il codice seguente al file della classe ISampleInterface per creare l'interfaccia ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="03a87-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
  
    namespace TypeEquivalenceInterface  
    {  
        [ComImport]  
        [Guid("8DA56996-A151-4136-B474-32784559F6DF")]  
        public interface ISampleInterface  
        {  
            void GetUserInput();  
            string UserInput { get; }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="03a87-153">Scegliere **Crea GUID** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="03a87-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="03a87-154">Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="03a87-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="03a87-155">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="03a87-155">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="03a87-156">Nell'attributo `Guid` eliminare il GUID di esempio e incollare il GUID copiato dalla finestra di dialogo **Crea GUID**.</span><span class="sxs-lookup"><span data-stu-id="03a87-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="03a87-157">Rimuovere le parentesi graffe ({}) dal GUID copiato.</span><span class="sxs-lookup"><span data-stu-id="03a87-157">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="03a87-158">In **Esplora soluzioni** espandere la cartella **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-158">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="03a87-159">Fare doppio clic sul file AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="03a87-159">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="03a87-160">Aggiungere il seguente attributo al file.</span><span class="sxs-lookup"><span data-stu-id="03a87-160">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="03a87-161">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="03a87-161">Save the file.</span></span>  
  
10. <span data-ttu-id="03a87-162">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03a87-162">Save the project.</span></span>  
  
11. <span data-ttu-id="03a87-163">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="03a87-163">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="03a87-164">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="03a87-164">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="03a87-165">Creare una classe di runtime</span><span class="sxs-lookup"><span data-stu-id="03a87-165">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="03a87-166">Per creare il progetto di runtime di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="03a87-166">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="03a87-167">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="03a87-167">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="03a87-168">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="03a87-168">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="03a87-169">Selezionare **Libreria di classi** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="03a87-169">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="03a87-170">Nella casella **Nome** digitare `TypeEquivalenceRuntime` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-170">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="03a87-171">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="03a87-171">The new project is created.</span></span>  
  
3.  <span data-ttu-id="03a87-172">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file Class1.cs e fare clic su **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="03a87-172">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="03a87-173">Rinominare il file `SampleClass.cs` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="03a87-173">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="03a87-174">Modificando il nome del file, anche la classe verrà rinominata `SampleClass`.</span><span class="sxs-lookup"><span data-stu-id="03a87-174">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="03a87-175">Questa classe implementerà l'interfaccia `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="03a87-175">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="03a87-176">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-176">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="03a87-177">Fare clic sulla scheda **Generazione**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="03a87-177">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="03a87-178">Durante la modifica delle proprietà del progetto scegliere la scheda **Firma**. Selezionare l opzione **Firma assembly**.</span><span class="sxs-lookup"><span data-stu-id="03a87-178">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="03a87-179">Nell'elenco **Scegli un file chiave con nome sicuro** fare clic su **<Nuovo…>**.</span><span class="sxs-lookup"><span data-stu-id="03a87-179">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="03a87-180">Nella casella **Nome file di chiave** digitare `key.snk`.</span><span class="sxs-lookup"><span data-stu-id="03a87-180">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="03a87-181">Deselezionare la casella di controllo **Proteggi file di chiave con una password**.</span><span class="sxs-lookup"><span data-stu-id="03a87-181">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="03a87-182">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-182">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="03a87-183">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="03a87-183">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="03a87-184">Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output.</span><span class="sxs-lookup"><span data-stu-id="03a87-184">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="03a87-185">Selezionare il file TypeEquivalenceInterface.dll e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-185">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="03a87-186">In **Esplora soluzioni** espandere la cartella **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="03a87-186">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="03a87-187">Selezionare il riferimento TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="03a87-187">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="03a87-188">Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Versione specifica** su **False**.</span><span class="sxs-lookup"><span data-stu-id="03a87-188">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="03a87-189">Aggiungere il codice seguente al file della classe SampleClass per creare la classe SampleClass.</span><span class="sxs-lookup"><span data-stu-id="03a87-189">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
  
    namespace TypeEquivalenceRuntime  
    {  
        public class SampleClass : ISampleInterface  
        {  
            private string p_UserInput;  
            public string UserInput { get { return p_UserInput; } }  
  
            public void GetUserInput()  
            {  
                Console.WriteLine("Please enter a value:");  
                p_UserInput = Console.ReadLine();  
            }  
        }  
    )  
    ```  
  
9. <span data-ttu-id="03a87-190">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03a87-190">Save the project.</span></span>  
  
10. <span data-ttu-id="03a87-191">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="03a87-191">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="03a87-192">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="03a87-192">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="03a87-193">Creare un progetto client</span><span class="sxs-lookup"><span data-stu-id="03a87-193">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="03a87-194">Per creare il progetto client di equivalenza del tipo</span><span class="sxs-lookup"><span data-stu-id="03a87-194">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="03a87-195">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="03a87-195">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="03a87-196">Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="03a87-196">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="03a87-197">Selezionare **Applicazione console** nel riquadro **Modelli**.</span><span class="sxs-lookup"><span data-stu-id="03a87-197">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="03a87-198">Nella casella **Nome** digitare `TypeEquivalenceClient` e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-198">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="03a87-199">Il nuovo progetto viene creato.</span><span class="sxs-lookup"><span data-stu-id="03a87-199">The new project is created.</span></span>  
  
3.  <span data-ttu-id="03a87-200">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-200">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="03a87-201">Fare clic sulla scheda **Generazione**. Impostare il percorso di output sullo stesso percorso usato nel progetto TypeEquivalenceInterface, ad esempio `C:\TypeEquivalenceSample`.</span><span class="sxs-lookup"><span data-stu-id="03a87-201">Click the **Build** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="03a87-202">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceClient e fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="03a87-202">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="03a87-203">Fare clic sulla scheda **Sfoglia** e passare alla cartella del percorso di output.</span><span class="sxs-lookup"><span data-stu-id="03a87-203">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="03a87-204">Selezionare il file TypeEquivalenceInterface.dll (non TypeEquivalenceRuntime.dll) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03a87-204">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="03a87-205">In **Esplora soluzioni** espandere la cartella **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="03a87-205">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="03a87-206">Selezionare il riferimento TypeEquivalenceInterface.</span><span class="sxs-lookup"><span data-stu-id="03a87-206">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="03a87-207">Nella finestra Proprietà del riferimento TypeEquivalenceInterface impostare la proprietà **Incorpora tipi di interoperabilità** su **True**.</span><span class="sxs-lookup"><span data-stu-id="03a87-207">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="03a87-208">Aggiungere il codice seguente al file Program.cs per creare il programma client.</span><span class="sxs-lookup"><span data-stu-id="03a87-208">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
    namespace TypeEquivalenceClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");  
                ISampleInterface sampleClass =   
                    (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");  
                sampleClass.GetUserInput();  
                Console.WriteLine(sampleClass.UserInput);  
                Console.WriteLine(sampleAssembly.GetName().Version.ToString());  
                Console.ReadLine();  
            }  
        }  
    }  
    ```  
  
7.  <span data-ttu-id="03a87-209">Premere CTRL+F5 per compilare ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="03a87-209">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="03a87-210">Modificare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="03a87-210">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="03a87-211">Per modificare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="03a87-211">To modify the interface</span></span>  
  
1.  <span data-ttu-id="03a87-212">In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="03a87-212">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="03a87-213">Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e quindi fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-213">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="03a87-214">Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="03a87-214">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="03a87-215">Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="03a87-215">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="03a87-216">Aprire il file ISampleInterface.cs.</span><span class="sxs-lookup"><span data-stu-id="03a87-216">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="03a87-217">Aggiungere la riga di codice seguente all'interfaccia ISampleInterface.</span><span class="sxs-lookup"><span data-stu-id="03a87-217">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="03a87-218">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="03a87-218">Save the file.</span></span>  
  
4.  <span data-ttu-id="03a87-219">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03a87-219">Save the project.</span></span>  
  
5.  <span data-ttu-id="03a87-220">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceInterface e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="03a87-220">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="03a87-221">Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="03a87-221">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="03a87-222">Modificare la classe di runtime</span><span class="sxs-lookup"><span data-stu-id="03a87-222">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="03a87-223">Per modificare la classe di runtime</span><span class="sxs-lookup"><span data-stu-id="03a87-223">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="03a87-224">In Visual Studio scegliere **Apri** dal menu **File** e quindi fare clic su **Progetto/Soluzione**.</span><span class="sxs-lookup"><span data-stu-id="03a87-224">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="03a87-225">Nella finestra di dialogo **Apri progetto** fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="03a87-225">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="03a87-226">Fare clic sulla scheda **Applicazione** . Fare clic sul pulsante **Informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="03a87-226">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="03a87-227">Modificare i valori di **Versione assembly** e **Versione file** in `2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="03a87-227">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="03a87-228">Aprire il file SampleClass.cs.</span><span class="sxs-lookup"><span data-stu-id="03a87-228">Open the SampleClass.cs file.</span></span> <span data-ttu-id="03a87-229">Aggiungere le seguenti righe di codice alla classe SampleClass.</span><span class="sxs-lookup"><span data-stu-id="03a87-229">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="03a87-230">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="03a87-230">Save the file.</span></span>  
  
4.  <span data-ttu-id="03a87-231">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="03a87-231">Save the project.</span></span>  
  
5.  <span data-ttu-id="03a87-232">Fare clic con il pulsante destro del mouse sul progetto TypeEquivalenceRuntime e fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="03a87-232">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="03a87-233">Una versione aggiornata del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione specificato in precedenza, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="03a87-233">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="03a87-234">In Esplora File aprire la cartella del percorso di output, ad esempio C:\TypeEquivalenceSample.</span><span class="sxs-lookup"><span data-stu-id="03a87-234">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="03a87-235">Fare doppio clic su TypeEquivalenceClient.exe per eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="03a87-235">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="03a87-236">Il programma rifletterà la nuova versione dell'assembly TypeEquivalenceRuntime senza dover essere ricompilato.</span><span class="sxs-lookup"><span data-stu-id="03a87-236">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a87-237">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03a87-237">See Also</span></span>  
 [<span data-ttu-id="03a87-238">/link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="03a87-238">/link (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)  
 [<span data-ttu-id="03a87-239">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="03a87-239">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="03a87-240">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="03a87-240">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="03a87-241">Assembly e Global Assembly Cache (C#)</span><span class="sxs-lookup"><span data-stu-id="03a87-241">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
