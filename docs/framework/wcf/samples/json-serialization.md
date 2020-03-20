---
title: Esempio DataContractJsonSerializer
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: d3456582d73640f1802c17d7f29f4931a6f920b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144630"
---
# <a name="datacontractjsonserializer-sample"></a>Esempio DataContractJsonSerializer

> [!NOTE]
> Questo esempio <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>è per . Per la maggior parte degli scenari che prevedono la serializzazione e la deserializzazione di JSON, è consigliabile utilizzare le API nello spazio dei [nomi System.Text.Json](../../../standard/serialization/system-text-json-overview.md).

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta gli stessi tipi dell'oggetto <xref:System.Runtime.Serialization.DataContractSerializer>. Il formato dati JSON è particolarmente utile quando si creano applicazioni Web di tipo AJAX (Asynchronous JavaScript and XML). Il supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il controllo ScriptManager. Per esempi su come utilizzare Windows Communication Foundation (WCF) con ASP.NET AJAX, vedere gli [esempi AJAX](ajax.md).  
  
La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
Nell'esempio viene utilizzato un contratto dati `Person` per illustrare la serializzazione e la deserializzazione.  

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

 Per serializzare un'istanza di tipo `Person` in formato JSON, creare prima l'elemento <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e utilizzare il metodo `WriteObject` per scrivere i dati JSON in un flusso.  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 Il flusso di memoria contiene dati JSON validi.
  
```json  
{"age":42,"name":"John"}  
```  
  
 Nell'esempio viene illustrata la deserializzazione da dati JSON a un oggetto. Si ritorna quindi all'inizio del flusso e si chiama `ReadObject`.  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 Esaminando l'oggetto `p2` si evince che i dati JSON sono stati deserializzati correttamente.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Compilare la soluzione JsonSerialization.sln come descritto in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2. Eseguire l'applicazione console risultante.  
