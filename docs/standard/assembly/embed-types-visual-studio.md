---
title: 'Procedura dettagliata: Incorporare i tipi da assembly gestiti in Visual Studio'
description: Questa procedura dettagliata illustra come incorporare i tipi da assembly gestiti in .NET usando Visual Studio. I tipi incorporati possono supportare l'indipendenza dalla versione.
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 636e5f8095b64cd0f445555c96d00945ccf7eaf8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378977"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="a0856-104">Procedura dettagliata: Incorporare i tipi da assembly gestiti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a0856-104">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="a0856-105">Se si incorporano informazioni sul tipo da un assembly gestito con nome sicuro, è possibile effettuare un accoppiamento debole dei tipi in un'applicazione per ottenere l'indipendenza dalla versione.</span><span class="sxs-lookup"><span data-stu-id="a0856-105">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="a0856-106">Ovvero, il programma può essere scritto in modo da usare i tipi di qualsiasi versione di una libreria gestita senza dover essere ricompilati per ogni nuova versione.</span><span class="sxs-lookup"><span data-stu-id="a0856-106">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="a0856-107">L'incorporamento dei tipi viene spesso usato con l'interoperabilità COM, ad esempio nel caso di un'applicazione che usa gli oggetti di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a0856-107">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="a0856-108">L'incorporamento di informazioni sul tipo consente alla stessa build di un programma di funzionare con versioni diverse di Microsoft Office in computer diversi.</span><span class="sxs-lookup"><span data-stu-id="a0856-108">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="a0856-109">Tuttavia, è anche possibile usare l'incorporamento dei tipi con soluzioni completamente gestite.</span><span class="sxs-lookup"><span data-stu-id="a0856-109">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="a0856-110">Dopo aver specificato le interfacce pubbliche che possono essere incorporate, è possibile creare classi di runtime che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="a0856-110">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="a0856-111">Un programma client può incorporare le informazioni sul tipo per le interfacce in fase di progettazione facendo riferimento all'assembly che contiene le interfacce pubbliche e impostando la `Embed Interop Types` proprietà del riferimento su `True` .</span><span class="sxs-lookup"><span data-stu-id="a0856-111">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="a0856-112">Il programma client può quindi caricare le istanze degli oggetti di runtime digitati come tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="a0856-112">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="a0856-113">Equivale a usare il compilatore della riga di comando e a fare riferimento all'assembly usando l' [opzione del compilatore-link](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a0856-113">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="a0856-114">Se si crea una nuova versione dell'assembly di runtime con nome sicuro, non è necessario ricompilare il programma client.</span><span class="sxs-lookup"><span data-stu-id="a0856-114">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="a0856-115">Il programma client continua a usare la versione dell'assembly di runtime disponibile, usando le informazioni sul tipo incorporate per le interfacce pubbliche.</span><span class="sxs-lookup"><span data-stu-id="a0856-115">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="a0856-116">Questa procedura dettagliata è costituita dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0856-116">In this walkthrough, you:</span></span>

1. <span data-ttu-id="a0856-117">Creare un assembly con nome sicuro con un'interfaccia pubblica che contiene informazioni sul tipo che possono essere incorporate.</span><span class="sxs-lookup"><span data-stu-id="a0856-117">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="a0856-118">Creare un assembly di runtime con nome sicuro che implementi l'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="a0856-118">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="a0856-119">Creare un programma client che incorpora le informazioni sul tipo dell'interfaccia pubblica e crea un'istanza della classe dall'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="a0856-119">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="a0856-120">Modificare e ricompilare l'assembly di runtime.</span><span class="sxs-lookup"><span data-stu-id="a0856-120">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="a0856-121">Eseguire il programma client per verificare che usi la nuova versione dell'assembly di runtime senza dover essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="a0856-121">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="a0856-122">Condizioni e limitazioni</span><span class="sxs-lookup"><span data-stu-id="a0856-122">Conditions and limitations</span></span>

<span data-ttu-id="a0856-123">È possibile incorporare le informazioni sul tipo da un assembly nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0856-123">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="a0856-124">L'assembly espone almeno un'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="a0856-124">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="a0856-125">Le interfacce incorporate sono annotate con `ComImport` attributi e `Guid` attributi con GUID univoci.</span><span class="sxs-lookup"><span data-stu-id="a0856-125">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="a0856-126">L'assembly viene annotato con l'attributo `ImportedFromTypeLib` o l'attributo `PrimaryInteropAssembly` e un attributo `Guid` a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="a0856-126">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="a0856-127">Per impostazione predefinita, i modelli di progetto Visual C# e Visual Basic includono un attributo a livello `Guid` di assembly.</span><span class="sxs-lookup"><span data-stu-id="a0856-127">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="a0856-128">Poiché la funzione primaria dell'incorporamento del tipo prevede il supporto di assembly di interoperabilità COM, quando si incorporano le informazioni sul tipo in una soluzione completamente gestita, si applicano le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a0856-128">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="a0856-129">Sono incorporati solo gli attributi specifici dell'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="a0856-129">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="a0856-130">Altri attributi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a0856-130">Other attributes are ignored.</span></span>
- <span data-ttu-id="a0856-131">Se un tipo USA parametri generici e il tipo del parametro generico è un tipo incorporato, tale tipo non può essere usato in un limite di assembly.</span><span class="sxs-lookup"><span data-stu-id="a0856-131">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="a0856-132">Esempi di superamento di un limite di assembly includono la chiamata a un metodo da un altro assembly o la derivazione di un tipo da un tipo definito in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="a0856-132">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="a0856-133">Le costanti non vengono incorporate.</span><span class="sxs-lookup"><span data-stu-id="a0856-133">Constants are not embedded.</span></span>
- <span data-ttu-id="a0856-134">La classe <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> non supporta un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="a0856-134">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="a0856-135">È possibile implementare un proprio tipo di dizionario per supportare un tipo incorporato come chiave.</span><span class="sxs-lookup"><span data-stu-id="a0856-135">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="a0856-136">Creare un'interfaccia</span><span class="sxs-lookup"><span data-stu-id="a0856-136">Create an interface</span></span>

<span data-ttu-id="a0856-137">Il primo passaggio consiste nel creare l'assembly dell'interfaccia di equivalenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="a0856-137">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="a0856-138">In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a0856-138">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a0856-139">Nella finestra di dialogo **Crea un nuovo progetto** Digitare *libreria di classi* nella casella **Cerca modelli** .</span><span class="sxs-lookup"><span data-stu-id="a0856-139">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="a0856-140">Selezionare il modello libreria di classi C# o Visual Basic **(.NET Framework)** nell'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0856-140">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="a0856-141">Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceInterface*e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a0856-141">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="a0856-142">Viene creato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-142">The new project is created.</span></span>

1. <span data-ttu-id="a0856-143">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1. vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *ISampleInterface*.</span><span class="sxs-lookup"><span data-stu-id="a0856-143">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="a0856-144">Rispondere **Sì** al prompt per rinominare anche la classe in `ISampleInterface` .</span><span class="sxs-lookup"><span data-stu-id="a0856-144">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="a0856-145">Questa classe rappresenta l'interfaccia pubblica per la classe.</span><span class="sxs-lookup"><span data-stu-id="a0856-145">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="a0856-146">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** , quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0856-146">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="a0856-147">Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** e impostare il **percorso di output** su un percorso nel computer, ad esempio *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a0856-147">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="a0856-148">Usare la stessa posizione in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="a0856-148">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="a0856-149">Selezionare **Signing (firma** ) nel riquadro a sinistra della schermata **Proprietà** , quindi selezionare la casella di controllo **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="a0856-149">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="a0856-150">Nell'elenco a discesa per **scegliere un file di chiave con nome sicuro**selezionare **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a0856-150">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="a0856-151">Nella finestra di dialogo **Crea chiave con nome sicuro** , in **nome file di chiave**, digitare *Key. snk*.</span><span class="sxs-lookup"><span data-stu-id="a0856-151">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="a0856-152">Deselezionare la casella **di controllo Proteggi file di chiave con una password** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-152">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="a0856-153">Aprire il file di classe *ISampleInterface* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare l' `ISampleInterface` interfaccia:</span><span class="sxs-lookup"><span data-stu-id="a0856-153">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

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

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. <span data-ttu-id="a0856-154">Scegliere **Crea GUID**dal menu **strumenti** , quindi nella finestra di dialogo **Crea GUID** selezionare **formato registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0856-154">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="a0856-155">Selezionare **copia**, quindi fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="a0856-155">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="a0856-156">Nell' `Guid` attributo del codice sostituire il GUID di esempio con il GUID copiato e rimuovere le parentesi graffe (**{}**).</span><span class="sxs-lookup"><span data-stu-id="a0856-156">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="a0856-157">In **Esplora soluzioni**espandere la cartella **Proprietà** e selezionare il file *AssemblyInfo.cs* o *AssemblyInfo. vb* .</span><span class="sxs-lookup"><span data-stu-id="a0856-157">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="a0856-158">Nell'editor di codice aggiungere l'attributo seguente al file:</span><span class="sxs-lookup"><span data-stu-id="a0856-158">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="a0856-159">Selezionare **file**  >  **Salva tutto** oppure premere **CTRL** + **MAIUSC** + **S** per salvare i file e il progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-159">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="a0856-160">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e selezionare **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a0856-160">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="a0856-161">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato, ad esempio *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a0856-161">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="a0856-162">Creare una classe di runtime</span><span class="sxs-lookup"><span data-stu-id="a0856-162">Create a runtime class</span></span>

<span data-ttu-id="a0856-163">Successivamente, creare la classe runtime di equivalenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="a0856-163">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="a0856-164">In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a0856-164">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a0856-165">Nella finestra di dialogo **Crea un nuovo progetto** Digitare *libreria di classi* nella casella **Cerca modelli** .</span><span class="sxs-lookup"><span data-stu-id="a0856-165">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="a0856-166">Selezionare il modello libreria di classi C# o Visual Basic **(.NET Framework)** nell'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0856-166">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="a0856-167">Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceRuntime*e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a0856-167">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="a0856-168">Viene creato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-168">The new project is created.</span></span>

1. <span data-ttu-id="a0856-169">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file *Class1.cs* o *Class1. vb* , scegliere **Rinomina**e rinominare il file da *Class1* a *SampleClass*.</span><span class="sxs-lookup"><span data-stu-id="a0856-169">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="a0856-170">Rispondere **Sì** al prompt per rinominare anche la classe in `SampleClass` .</span><span class="sxs-lookup"><span data-stu-id="a0856-170">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="a0856-171">La classe implementa l'interfaccia `ISampleInterface`.</span><span class="sxs-lookup"><span data-stu-id="a0856-171">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="a0856-172">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0856-172">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="a0856-173">Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** , quindi impostare il **percorso di output** sullo stesso percorso usato per il progetto TypeEquivalenceInterface, ad esempio *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a0856-173">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="a0856-174">Selezionare **Signing (firma** ) nel riquadro a sinistra della schermata **Proprietà** , quindi selezionare la casella di controllo **Firma assembly** .</span><span class="sxs-lookup"><span data-stu-id="a0856-174">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="a0856-175">Nell'elenco a discesa per **scegliere un file di chiave con nome sicuro**selezionare **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a0856-175">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="a0856-176">Nella finestra di dialogo **Crea chiave con nome sicuro** , in **nome file di chiave**, digitare *Key. snk*.</span><span class="sxs-lookup"><span data-stu-id="a0856-176">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="a0856-177">Deselezionare la casella **di controllo Proteggi file di chiave con una password** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-177">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="a0856-178">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **Aggiungi**  >  **riferimento**.</span><span class="sxs-lookup"><span data-stu-id="a0856-178">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="a0856-179">Nella finestra di dialogo **Gestione riferimenti** selezionare **Sfoglia** e passare alla cartella percorso di output.</span><span class="sxs-lookup"><span data-stu-id="a0856-179">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="a0856-180">Selezionare il file *TypeEquivalenceInterface. dll* , selezionare **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-180">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="a0856-181">In **Esplora soluzioni**espandere la cartella **riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** .</span><span class="sxs-lookup"><span data-stu-id="a0856-181">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="a0856-182">Nel riquadro **Proprietà** impostare **versione specifica** su **false** se non è già presente.</span><span class="sxs-lookup"><span data-stu-id="a0856-182">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="a0856-183">Aprire il file di classe *SampleClass* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare la `SampleClass` classe:</span><span class="sxs-lookup"><span data-stu-id="a0856-183">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

   ```csharp
   using System;
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
   }
   ```

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

1. <span data-ttu-id="a0856-184">Selezionare **file**  >  **Salva tutto** oppure premere **CTRL** + **MAIUSC** + **S** per salvare i file e il progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-184">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="a0856-185">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e selezionare **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a0856-185">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="a0856-186">Il file DLL della libreria di classi viene compilato e salvato nel percorso dell'output di compilazione specificato.</span><span class="sxs-lookup"><span data-stu-id="a0856-186">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="a0856-187">Creazione di un progetto client</span><span class="sxs-lookup"><span data-stu-id="a0856-187">Create a client project</span></span>

<span data-ttu-id="a0856-188">Infine, creare un programma client di equivalenza del tipo che fa riferimento all'assembly dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a0856-188">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="a0856-189">In Visual Studio selezionare **File** > **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a0856-189">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a0856-190">Nella finestra di dialogo **Crea un nuovo progetto** Digitare *console* nella casella **Cerca modelli** .</span><span class="sxs-lookup"><span data-stu-id="a0856-190">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="a0856-191">Selezionare il modello applicazione console C# o Visual Basic **(.NET Framework)** dall'elenco e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0856-191">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="a0856-192">Nella finestra di dialogo **Configura nuovo progetto** , in **nome progetto**, digitare *TypeEquivalenceClient*e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a0856-192">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="a0856-193">Viene creato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-193">The new project is created.</span></span>

1. <span data-ttu-id="a0856-194">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0856-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="a0856-195">Selezionare **Compila** nel riquadro sinistro della schermata **Proprietà** , quindi impostare il **percorso di output** sullo stesso percorso usato per il progetto TypeEquivalenceInterface, ad esempio *C:\TypeEquivalenceSample*.</span><span class="sxs-lookup"><span data-stu-id="a0856-195">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="a0856-196">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceClient** e scegliere **Aggiungi**  >  **riferimento**.</span><span class="sxs-lookup"><span data-stu-id="a0856-196">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="a0856-197">Se il file **TypeEquivalenceInterface. dll** è già elencato nella finestra di dialogo **Gestione riferimenti** , selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="a0856-197">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="a0856-198">In caso contrario, selezionare **Sfoglia**, passare alla cartella percorso output, selezionare il file *TypeEquivalenceInterface. dll* (non *TypeEquivalenceRuntime. dll*) e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a0856-198">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="a0856-199">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-199">Select **OK**.</span></span>

1. <span data-ttu-id="a0856-200">In **Esplora soluzioni**espandere la cartella **riferimenti** e selezionare il riferimento **TypeEquivalenceInterface** .</span><span class="sxs-lookup"><span data-stu-id="a0856-200">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="a0856-201">Nel riquadro **Proprietà** impostare **Incorpora tipi di interoperabilità** su **true**.</span><span class="sxs-lookup"><span data-stu-id="a0856-201">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="a0856-202">Aprire il file *Program.cs* o *Module1. vb* nell'editor di codice e sostituirne il contenuto con il codice seguente per creare il programma client:</span><span class="sxs-lookup"><span data-stu-id="a0856-202">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

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

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

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

1. <span data-ttu-id="a0856-203">Selezionare **file**  >  **Salva tutto** oppure premere **CTRL** + **MAIUSC** + **S** per salvare i file e il progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-203">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="a0856-204">Premere **CTRL** + **F5** per compilare ed eseguire il programma.</span><span class="sxs-lookup"><span data-stu-id="a0856-204">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="a0856-205">Si noti che l'output della console restituisce l'assembly versione **1.0.0.0**.</span><span class="sxs-lookup"><span data-stu-id="a0856-205">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="a0856-206">Modificare l'interfaccia</span><span class="sxs-lookup"><span data-stu-id="a0856-206">Modify the interface</span></span>

<span data-ttu-id="a0856-207">Modificare ora l'assembly dell'interfaccia e modificarne la versione.</span><span class="sxs-lookup"><span data-stu-id="a0856-207">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="a0856-208">In Visual Studio selezionare **file**  >  **Apri**  >  **progetto/soluzione**e aprire il progetto **TypeEquivalenceInterface** .</span><span class="sxs-lookup"><span data-stu-id="a0856-208">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="a0856-209">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0856-209">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="a0856-210">Selezionare **applicazione** nel riquadro sinistro della schermata **Proprietà** , quindi selezionare **informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="a0856-210">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="a0856-211">Nella finestra di dialogo **informazioni assembly** modificare i valori versione **assembly** e **versione file** in *2.0.0.0*, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-211">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="a0856-212">Aprire il file *SampleInterface.cs* o *SampleInterface. vb* e aggiungere la riga di codice seguente all' `ISampleInterface` interfaccia:</span><span class="sxs-lookup"><span data-stu-id="a0856-212">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="a0856-213">Selezionare **file**  >  **Salva tutto** oppure premere **CTRL** + **MAIUSC** + **S** per salvare i file e il progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-213">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="a0856-214">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceInterface** e selezionare **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a0856-214">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="a0856-215">Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a0856-215">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="a0856-216">Modificare la classe di runtime</span><span class="sxs-lookup"><span data-stu-id="a0856-216">Modify the runtime class</span></span>

<span data-ttu-id="a0856-217">Modificare anche la classe runtime e aggiornarne la versione.</span><span class="sxs-lookup"><span data-stu-id="a0856-217">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="a0856-218">In Visual Studio selezionare **file**  >  **Apri**  >  **progetto/soluzione**e aprire il progetto **TypeEquivalenceRuntime** .</span><span class="sxs-lookup"><span data-stu-id="a0856-218">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="a0856-219">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a0856-219">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="a0856-220">Selezionare **applicazione** nel riquadro sinistro della schermata **Proprietà** , quindi selezionare **informazioni assembly**.</span><span class="sxs-lookup"><span data-stu-id="a0856-220">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="a0856-221">Nella finestra di dialogo **informazioni assembly** modificare i valori versione **assembly** e **versione file** in *2.0.0.0*, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0856-221">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="a0856-222">Aprire il file *SampleClass.cs* o *SampleClass. vb* e aggiungere il codice seguente alla `SampleClass` classe:</span><span class="sxs-lookup"><span data-stu-id="a0856-222">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. <span data-ttu-id="a0856-223">Selezionare **file**  >  **Salva tutto** oppure premere **CTRL** + **MAIUSC** + **S** per salvare i file e il progetto.</span><span class="sxs-lookup"><span data-stu-id="a0856-223">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="a0856-224">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **TypeEquivalenceRuntime** e selezionare **Compila**.</span><span class="sxs-lookup"><span data-stu-id="a0856-224">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="a0856-225">Una nuova versione del file DLL della libreria di classi viene compilata e salvata nel percorso dell'output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a0856-225">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="a0856-226">Eseguire il programma client aggiornato</span><span class="sxs-lookup"><span data-stu-id="a0856-226">Run the updated client program</span></span>

<span data-ttu-id="a0856-227">Passare al percorso della cartella di output di compilazione ed eseguire *TypeEquivalenceClient. exe*.</span><span class="sxs-lookup"><span data-stu-id="a0856-227">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="a0856-228">Si noti che l'output della console ora riflette la nuova versione dell' `TypeEquivalenceRuntime` assembly, *2.0.0.0*, senza il programma da ricompilare.</span><span class="sxs-lookup"><span data-stu-id="a0856-228">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0856-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0856-229">See also</span></span>

- [<span data-ttu-id="a0856-230">-link (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="a0856-230">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="a0856-231">-collegamento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0856-231">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="a0856-232">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a0856-232">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a0856-233">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0856-233">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="a0856-234">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="a0856-234">Assemblies in .NET</span></span>](index.md)
