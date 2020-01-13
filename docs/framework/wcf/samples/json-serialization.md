---
title: Esempio di DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 52e10ee28137b16bd90e6f3f3ac41f839528f334
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904533"
---
# <a name="datacontractjsonserializer-sample"></a><span data-ttu-id="88306-102">Esempio di DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="88306-102">DataContractJsonSerializer sample</span></span>

> [!NOTE]
> <span data-ttu-id="88306-103">Questo esempio è per <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="88306-103">This sample is for <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="88306-104">Per la maggior parte degli scenari che coinvolgono la serializzazione e la deserializzazione di JSON, è consigliabile usare le API nello [spazio dei nomi System. Text. JSON](../../../standard/serialization/system-text-json-overview.md).</span><span class="sxs-lookup"><span data-stu-id="88306-104">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span> 

<span data-ttu-id="88306-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta gli stessi tipi dell'oggetto <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="88306-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="88306-106">Il formato dati JSON è particolarmente utile quando si creano applicazioni Web di tipo AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="88306-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="88306-107">Il supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo ScriptManager.</span><span class="sxs-lookup"><span data-stu-id="88306-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="88306-108">Per esempi relativi all'uso di Windows Communication Foundation (WCF) con ASP.NET AJAX, vedere gli [esempi di AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="88306-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
<span data-ttu-id="88306-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="88306-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
<span data-ttu-id="88306-110">Nell'esempio viene utilizzato un contratto dati `Person` per illustrare la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="88306-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

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

 <span data-ttu-id="88306-111">Per serializzare un'istanza di tipo `Person` in formato JSON, creare prima l'elemento <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e utilizzare il metodo `WriteObject` per scrivere i dati JSON in un flusso.</span><span class="sxs-lookup"><span data-stu-id="88306-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="88306-112">Il flusso di memoria contiene dati JSON validi.</span><span class="sxs-lookup"><span data-stu-id="88306-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="88306-113">Nell'esempio viene illustrata la deserializzazione da dati JSON a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="88306-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="88306-114">Si ritorna quindi all'inizio del flusso e si chiama `ReadObject`.</span><span class="sxs-lookup"><span data-stu-id="88306-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="88306-115">Esaminando l'oggetto `p2` si evince che i dati JSON sono stati deserializzati correttamente.</span><span class="sxs-lookup"><span data-stu-id="88306-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="88306-116">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="88306-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="88306-117">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="88306-117">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="88306-118">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="88306-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="88306-119">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="88306-119">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="88306-120">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="88306-120">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="88306-121">Compilare la soluzione JsonSerialization. sln come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="88306-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="88306-122">Eseguire l'applicazione console risultante.</span><span class="sxs-lookup"><span data-stu-id="88306-122">Run the resulting console application.</span></span>  
