---
title: Esempio di DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 1711c826397dfb8b54ecedee08e88e67cb58d2a4
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180233"
---
# <a name="datacontractjsonserializer-sample"></a><span data-ttu-id="37345-102">Esempio di DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="37345-102">DataContractJsonSerializer sample</span></span>
<span data-ttu-id="37345-103">In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per serializzare e deserializzare i dati nel formato JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="37345-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="37345-104">Questo motore di serializzazione converte i dati JSON in istanze di tipi di .NET Framework e di nuovo nei dati JSON.</span><span class="sxs-lookup"><span data-stu-id="37345-104">This serialization engine converts JSON data into instances of .NET Framework types and back into JSON data.</span></span> <span data-ttu-id="37345-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta gli stessi tipi dell'oggetto <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="37345-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="37345-106">Il formato dati JSON è particolarmente utile quando si creano applicazioni Web di tipo AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="37345-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="37345-107">Il supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo ScriptManager.</span><span class="sxs-lookup"><span data-stu-id="37345-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="37345-108">Per esempi relativi all'uso di Windows Communication Foundation (WCF) con ASP.NET AJAX, vedere gli [esempi di AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="37345-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37345-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="37345-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="37345-110">Nell'esempio viene utilizzato un contratto dati `Person` per illustrare la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="37345-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 <span data-ttu-id="37345-111">Per serializzare un'istanza di tipo `Person` in formato JSON, creare prima l'elemento <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e utilizzare il metodo `WriteObject` per scrivere i dati JSON in un flusso.</span><span class="sxs-lookup"><span data-stu-id="37345-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="37345-112">Il flusso di memoria contiene dati JSON validi.</span><span class="sxs-lookup"><span data-stu-id="37345-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="37345-113">Nell'esempio viene illustrata la deserializzazione da dati JSON a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="37345-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="37345-114">Si ritorna quindi all'inizio del flusso e si chiama `ReadObject`.</span><span class="sxs-lookup"><span data-stu-id="37345-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="37345-115">Esaminando l'oggetto `p2` si evince che i dati JSON sono stati deserializzati correttamente.</span><span class="sxs-lookup"><span data-stu-id="37345-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37345-116">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="37345-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="37345-117">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="37345-117">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="37345-118">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37345-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="37345-119">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="37345-119">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="37345-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="37345-120">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="37345-121">Compilare la soluzione JsonSerialization. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="37345-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="37345-122">Eseguire l'applicazione console risultante.</span><span class="sxs-lookup"><span data-stu-id="37345-122">Run the resulting console application.</span></span>  
