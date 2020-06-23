---
title: Esempio di DataContractSerializer
description: In questo esempio viene illustrato DataContractSerializer in WCF, che esegue Servizi generali di serializzazione e deserializzazione per le classi del contratto dati.
ms.date: 03/30/2017
helpviewer_keywords:
- XML Formatter
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
ms.openlocfilehash: c2f62c8926f09e2d4cdea1941909e7d8f59c43a0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244400"
---
# <a name="datacontractserializer-sample"></a><span data-ttu-id="afb25-103">Esempio di DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="afb25-103">DataContractSerializer Sample</span></span>
<span data-ttu-id="afb25-104">Nell'esempio relativo a DataContractSerializer viene illustrata la classe <xref:System.Runtime.Serialization.DataContractSerializer>, che esegue servizi generali di serializzazione e di deserializzazione per le classi del contratto dati.</span><span class="sxs-lookup"><span data-stu-id="afb25-104">The DataContractSerializer sample demonstrates the <xref:System.Runtime.Serialization.DataContractSerializer>, which performs general serialization and deserialization services for the data contract classes.</span></span> <span data-ttu-id="afb25-105">Nell'esempio viene creato un `Record` oggetto, viene serializzato in un flusso di memoria e il flusso di memoria viene deserializzato in un altro `Record` oggetto per illustrare l'utilizzo di <xref:System.Runtime.Serialization.DataContractSerializer> .</span><span class="sxs-lookup"><span data-stu-id="afb25-105">The sample creates a `Record` object, serializes it to a memory stream and deserializes the memory stream back to another `Record` object to demonstrate the use of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="afb25-106">L'esempio serializza quindi l'oggetto `Record` usando un writer binario per illustrare come il writer influisce sulla serializzazione.</span><span class="sxs-lookup"><span data-stu-id="afb25-106">The sample then serializes the `Record` object using a binary writer to demonstrate how the writer affects serialization.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afb25-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="afb25-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="afb25-108">Il contratto dati per `Record` viene illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="afb25-108">The data contract for `Record` is shown in the following sample code.</span></span>  
  
```csharp  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return $"Record: {n1} {operation} {n2} = {result}";
    }  
}  
```  
  
 <span data-ttu-id="afb25-109">L'esempio di codice crea un oggetto `Record` denominato `record1`, quindi visualizza l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="afb25-109">The sample code creates a `Record` object named `record1` then displays the object.</span></span>  
  
```csharp
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
```  
  
 <span data-ttu-id="afb25-110">L'esempio usa quindi <xref:System.Runtime.Serialization.DataContractSerializer> per serializzare `record1` in un flusso di memoria.</span><span class="sxs-lookup"><span data-stu-id="afb25-110">The sample then uses the <xref:System.Runtime.Serialization.DataContractSerializer> to serialize `record1` into a memory stream.</span></span>  
  
```csharp  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
```  
  
 <span data-ttu-id="afb25-111">L'esempio usa quindi <xref:System.Runtime.Serialization.DataContractSerializer> per deserializzare di nuovo il flusso di memoria in un nuovo oggetto `Record` e lo visualizza.</span><span class="sxs-lookup"><span data-stu-id="afb25-111">Next, the sample uses the <xref:System.Runtime.Serialization.DataContractSerializer> to deserialize the memory stream back into a new `Record` object and displays it.</span></span>  
  
```csharp  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
```  
  
 <span data-ttu-id="afb25-112">Per impostazione predefinita, `DataContractSerializer` codifica gli oggetti in un flusso usando una rappresentazione testuale di XML.</span><span class="sxs-lookup"><span data-stu-id="afb25-112">By default, the `DataContractSerializer` encodes objects into a stream using a textual representation of XML.</span></span> <span data-ttu-id="afb25-113">Tuttavia, è possibile influenzare la codifica del XML usando un writer diverso.</span><span class="sxs-lookup"><span data-stu-id="afb25-113">However, you can influence the encoding of the XML by passing in a different writer.</span></span> <span data-ttu-id="afb25-114">Nell'esempio viene creato un writer binario chiamando <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span><span class="sxs-lookup"><span data-stu-id="afb25-114">The sample creates a binary writer by calling <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span></span> <span data-ttu-id="afb25-115">Il writer e l'oggetto record vengono quindi passati al serializzatore quando chiama <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span><span class="sxs-lookup"><span data-stu-id="afb25-115">It then passes the writer and the record object to the serializer when it calls <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span></span> <span data-ttu-id="afb25-116">Infine, l'esempio scarica il writer e segnala la lunghezza dei flussi.</span><span class="sxs-lookup"><span data-stu-id="afb25-116">Finally, the sample flushes the writer and reports on the length of the streams.</span></span>  
  
```csharp  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 <span data-ttu-id="afb25-117">Quando si esegue l'esempio, vengono visualizzati il record originale e il record deserializzato, seguiti dal confronto tra la lunghezza della codifica del testo e della codifica binaria.</span><span class="sxs-lookup"><span data-stu-id="afb25-117">When you run the sample, the original record and the deserialized record are displayed, followed by the comparison between the length of the text encoding and the binary encoding.</span></span> <span data-ttu-id="afb25-118">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="afb25-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="afb25-119">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="afb25-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="afb25-120">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="afb25-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="afb25-121">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="afb25-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="afb25-122">Per eseguire l'esempio, avviare il client dal prompt dei comandi digitando client\bin\client.exe.</span><span class="sxs-lookup"><span data-stu-id="afb25-122">To run the sample, start the client from the command prompt by typing client\bin\client.exe.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="afb25-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="afb25-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="afb25-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="afb25-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="afb25-125">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="afb25-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="afb25-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="afb25-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
