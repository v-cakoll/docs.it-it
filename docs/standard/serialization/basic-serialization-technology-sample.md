---
title: Esempio di tecnologia di serializzazione di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c3d269b7603c63db73fdcbab91b777e69b228cc9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="f3af6-102">Esempio di tecnologia di serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="f3af6-102">Basic Serialization Technology Sample</span></span>
[<span data-ttu-id="f3af6-103">Scaricare l'esempio</span><span class="sxs-lookup"><span data-stu-id="f3af6-103">Download sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)  
  
 <span data-ttu-id="f3af6-104">In questo esempio viene illustrata la capacità di Common Language Runtime di serializzare in un flusso il grafico di un oggetto contenuto in memoria.</span><span class="sxs-lookup"><span data-stu-id="f3af6-104">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="f3af6-105">Per la serializzazione, è possibile utilizzare l'oggetto <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="f3af6-105">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="f3af6-106">Un elenco collegato, contenente dati, viene serializzato in un flusso di file o deserializzato da tale flusso.</span><span class="sxs-lookup"><span data-stu-id="f3af6-106">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="f3af6-107">In entrambi i casi l'elenco viene visualizzato per consentire di esaminare i risultati.</span><span class="sxs-lookup"><span data-stu-id="f3af6-107">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="f3af6-108">L'elenco collegato è di tipo `LinkedList`, un tipo definito in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="f3af6-108">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>  
  
 <span data-ttu-id="f3af6-109">Per ulteriori informazioni sulla serializzazione, vedere i commenti nei file di codice sorgente e build.proj.</span><span class="sxs-lookup"><span data-stu-id="f3af6-109">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="f3af6-110">Per compilare l'esempio utilizzando il prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="f3af6-110">To build the sample using the Command Prompt</span></span>  
  
1.  <span data-ttu-id="f3af6-111">Spostarsi in una delle sottodirectory specifiche del linguaggio della directory Technologies\Serialization\Runtime Serialization\Basic utilizzando il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f3af6-111">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>  
  
2.  <span data-ttu-id="f3af6-112">Dalla riga di comando digitare **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, a seconda del linguaggio di programmazione che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="f3af6-112">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="f3af6-113">Per compilare l'esempio utilizzando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3af6-113">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="f3af6-114">Aprire [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)], quindi spostarsi in una delle sottodirectory specifiche del linguaggio relative all'esempio.</span><span class="sxs-lookup"><span data-stu-id="f3af6-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="f3af6-115">Fare doppio clic sull'icona relativa a SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, a seconda del linguaggio di programmazione che si desidera utilizzare, per aprire il file in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f3af6-115">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="f3af6-116">Scegliere **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="f3af6-116">In the **Build** menu, select **Build Solution**.</span></span>  
  
 <span data-ttu-id="f3af6-117">L'applicazione verrà compilata nella sottodirectory predefinita \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="f3af6-117">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="f3af6-118">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="f3af6-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="f3af6-119">Spostarsi nella directory contenente l'eseguibile compilato.</span><span class="sxs-lookup"><span data-stu-id="f3af6-119">Navigate to the directory containing the built executable.</span></span>  
  
2.  <span data-ttu-id="f3af6-120">Dalla riga di comando digitare **Serialization.exe** con i valori di parametro desiderati.</span><span class="sxs-lookup"><span data-stu-id="f3af6-120">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f3af6-121">L'esempio compila un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="f3af6-121">This sample builds a console application.</span></span> <span data-ttu-id="f3af6-122">Per visualizzare l'output dell'applicazione, è necessario avviarla dalla finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f3af6-122">You must launch it using the command prompt in order to view its output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3af6-123">Note</span><span class="sxs-lookup"><span data-stu-id="f3af6-123">Remarks</span></span>  
 <span data-ttu-id="f3af6-124">L'applicazione di esempio accetta parametri della riga di comando che indicano il test da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f3af6-124">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="f3af6-125">Per serializzare un elenco costituito da 10 nodi in un file denominato **Test.xml** tramite il formattatore SOAP, usare i parametri **sx Test.xml 10**.</span><span class="sxs-lookup"><span data-stu-id="f3af6-125">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>  
  
 <span data-ttu-id="f3af6-126">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="f3af6-126">For Example:</span></span>  
  
 <span data-ttu-id="f3af6-127">**Serialize.exe -sx Test.xml 10**</span><span class="sxs-lookup"><span data-stu-id="f3af6-127">**Serialize.exe -sx Test.xml 10**</span></span>  
  
 <span data-ttu-id="f3af6-128">Per deserializzare il file **Test.xml** dell'esempio precedente, usare i parametri **dx Test.xml**.</span><span class="sxs-lookup"><span data-stu-id="f3af6-128">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>  
  
 <span data-ttu-id="f3af6-129">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="f3af6-129">For Example:</span></span>  
  
 <span data-ttu-id="f3af6-130">**Serialize.exe -dx Test.xml**</span><span class="sxs-lookup"><span data-stu-id="f3af6-130">**Serialize.exe -dx Test.xml**</span></span>  
  
 <span data-ttu-id="f3af6-131">Nei due esempi precedenti, la lettera "x" nell'opzione della riga di comando indica che si desidera utilizzare la serializzazione SOAP XML.</span><span class="sxs-lookup"><span data-stu-id="f3af6-131">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="f3af6-132">Per utilizzare la serializzazione binaria, è possibile utilizzare la lettera "b".</span><span class="sxs-lookup"><span data-stu-id="f3af6-132">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="f3af6-133">Se si desidera eseguire la serializzazione con un numero di nodi molto elevato, può essere opportuno reindirizzare l'output della console in un file.</span><span class="sxs-lookup"><span data-stu-id="f3af6-133">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>  
  
 <span data-ttu-id="f3af6-134">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="f3af6-134">For Example:</span></span>  
  
 <span data-ttu-id="f3af6-135">**Serialize.exe -sb Test.bin 10000 >somefile.txt**</span><span class="sxs-lookup"><span data-stu-id="f3af6-135">**Serialize.exe -sb Test.bin 10000 >somefile.txt**</span></span>  
  
 <span data-ttu-id="f3af6-136">Nell'elenco riportato di seguito vengono descritte in modo sintetico le classi e le tecnologie utilizzate nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f3af6-136">The following bullets briefly describe the classes and technologies used by this sample.</span></span>  
  
-   <span data-ttu-id="f3af6-137">Serializzazione in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="f3af6-137">Runtime Serialization</span></span>  
  
    -   <span data-ttu-id="f3af6-138"><xref:System.Runtime.Serialization.IFormatter> - Consente di fare riferimento a un oggetto <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="f3af6-138"><xref:System.Runtime.Serialization.IFormatter> Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>  
  
    -   <span data-ttu-id="f3af6-139"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> - Consente di serializzare un elenco collegato in un flusso in formato binario.</span><span class="sxs-lookup"><span data-stu-id="f3af6-139"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="f3af6-140">Il formattatore binario utilizza un formato riconosciuto solo dal tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="f3af6-140">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="f3af6-141">Tuttavia, i dati sono concisi.</span><span class="sxs-lookup"><span data-stu-id="f3af6-141">However, the data is concise.</span></span>  
  
    -   <span data-ttu-id="f3af6-142"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> - Consente di serializzare un elenco collegato in un flusso in formato SOAP,</span><span class="sxs-lookup"><span data-stu-id="f3af6-142"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="f3af6-143">che è un formato standard.</span><span class="sxs-lookup"><span data-stu-id="f3af6-143">SOAP is a standard format.</span></span>  
  
-   <span data-ttu-id="f3af6-144">I/O di flusso</span><span class="sxs-lookup"><span data-stu-id="f3af6-144">Stream I/O</span></span>  
  
    -   <span data-ttu-id="f3af6-145"><xref:System.IO.Stream> - Consente di eseguire la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="f3af6-145"><xref:System.IO.Stream> Used to serialize and deserialize.</span></span> <span data-ttu-id="f3af6-146">Il tipo di flusso specifico utilizzato in questo esempio è <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="f3af6-146">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="f3af6-147">È tuttavia possibile utilizzare la serializzazione con qualsiasi tipo derivato da <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f3af6-147">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>  
  
    -   <span data-ttu-id="f3af6-148"><xref:System.IO.File> - Consente di creare oggetti <xref:System.IO.FileStream> per la lettura e la creazione di file su disco.</span><span class="sxs-lookup"><span data-stu-id="f3af6-148"><xref:System.IO.File> Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>  
  
    -   <span data-ttu-id="f3af6-149"><xref:System.IO.FileStream> - Consente di eseguire la serializzazione e la deserializzazione di elenchi collegati.</span><span class="sxs-lookup"><span data-stu-id="f3af6-149"><xref:System.IO.FileStream> Used to serialize and deserialize linked lists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3af6-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3af6-150">See Also</span></span>  
 <xref:System.IO>  
 <xref:System.IO.File>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.Stream>  
 <xref:System.Random>  
 <xref:System.Runtime.Serialization>  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
 <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>  
 <xref:System.Runtime.Serialization.IFormatter>  
 <xref:System.SerializableAttribute>  
 <xref:System.Xml.Serialization>  
 [<span data-ttu-id="f3af6-151">Serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="f3af6-151">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)  
 [<span data-ttu-id="f3af6-152">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="f3af6-152">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)  
 [<span data-ttu-id="f3af6-153">Controllo della serializzazione XML mediante attributi</span><span class="sxs-lookup"><span data-stu-id="f3af6-153">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)  
 [<span data-ttu-id="f3af6-154">Introduzione alla serializzazione XML</span><span class="sxs-lookup"><span data-stu-id="f3af6-154">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="f3af6-155">Serializzazione</span><span class="sxs-lookup"><span data-stu-id="f3af6-155">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="f3af6-156">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="f3af6-156">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
