---
title: Serializzazione JSON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9c270740eda992653fc4e60072f1276cf20ad584
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="json-serialization"></a>Serializzazione JSON
In questo esempio viene illustrato come utilizzare <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> per serializzare e deserializzare i dati nel formato JSON (JavaScript Object Notation). Questo motore della serializzazione converte i dati JSON in istanze dei tipi [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] e li riconverte in dati JSON. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supporta gli stessi tipi dell'oggetto <xref:System.Runtime.Serialization.DataContractSerializer>. Il formato dati JSON è particolarmente utile quando si creano applicazioni Web di tipo AJAX (Asynchronous JavaScript and XML). Il supporto AJAX in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è ottimizzato per l'utilizzo con ASP.NET AJAX tramite il controllo ScriptManager. Per esempi di come utilizzare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con ASP.NET AJAX, vedere il [esempi AJAX](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene utilizzato un contratto dati `Person` per illustrare la serializzazione e la deserializzazione.  
  
```  
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
  
```  
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
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 Esaminando l'oggetto `p2` si evince che i dati JSON sono stati deserializzati correttamente.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Compilare la soluzione JsonSerialization.sln, come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Eseguire l'applicazione console risultante.  
  
## <a name="see-also"></a>Vedere anche
