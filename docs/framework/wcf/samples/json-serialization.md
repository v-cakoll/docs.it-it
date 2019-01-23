---
title: Serializzazione JSON
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: 7e46ef640215aee48bdebe892f161d403d1a3e73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523311"
---
# <a name="json-serialization"></a>Serializzazione JSON
In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per serializzare e deserializzare i dati nel formato JSON (JavaScript Object Notation). Questo motore della serializzazione converte i dati JSON in istanze dei tipi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] e li riconverte in dati JSON. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta gli stessi tipi dell'oggetto <xref:System.Runtime.Serialization.DataContractSerializer>. Il formato dati JSON è particolarmente utile quando si creano applicazioni Web di tipo AJAX (Asynchronous JavaScript and XML). Supporto AJAX in Windows Communication Foundation (WCF) è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il controllo ScriptManager. Per esempi di come usare Windows Communication Foundation (WCF) con ASP.NET AJAX, vedere la [esempi AJAX](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
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
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Compilare la soluzione jsonSerialization come descritto in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Eseguire l'applicazione console risultante.  
  
## <a name="see-also"></a>Vedere anche
