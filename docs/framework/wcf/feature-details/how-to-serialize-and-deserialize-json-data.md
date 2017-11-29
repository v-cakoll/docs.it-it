---
title: 'Procedura: serializzare e deserializzare dati JSON'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 14029250f3bc26ff8598e0b8d4ccce8e9fcca331
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="bc63e-102">Procedura: serializzare e deserializzare dati JSON</span><span class="sxs-lookup"><span data-stu-id="bc63e-102">How to: Serialize and Deserialize JSON Data</span></span>
<span data-ttu-id="bc63e-103">JSON (JavaScript Object Notation) è un efficiente formato di codifica dati che consente scambi rapidi di piccole quantità di dati tra browser client e servizi Web compatibili con AJAX.</span><span class="sxs-lookup"><span data-stu-id="bc63e-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="bc63e-104">In questo argomento viene descritto come serializzare oggetti di tipo .NET in dati con codifica JSON e quindi come deserializzare i dati in formato JSON in istanze di tipi .NET utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bc63e-104">This topic demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="bc63e-105">In questo esempio viene utilizzato un contratto dati per illustrare la serializzazione e la deserializzazione di un tipo `Person` definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bc63e-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type.</span></span>  
  
 <span data-ttu-id="bc63e-106">In genere, la serializzazione e la deserializzazione JSON vengono gestite automaticamente da [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] quando si utilizzano tipi di contratto dati nelle operazioni del servizio esposte su endpoint compatibili con AJAX.</span><span class="sxs-lookup"><span data-stu-id="bc63e-106">Normally, JSON serialization and deserialization is handled automatically by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="bc63e-107">Tuttavia, in alcuni casi potrebbe essere necessario utilizzare direttamente dati JSON, come nel caso dello scenario descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bc63e-107">However, in some cases you may need to work with JSON data directly - this is the scenario that this topic demonstrates.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc63e-108">Se si verifica un errore durante la serializzazione di una risposta in uscita nel server o se l'operazione di risposta genera un'eccezione per qualche altro motivo, è possibile che l'errore non venga restituito al client.</span><span class="sxs-lookup"><span data-stu-id="bc63e-108">If an error occurs during serialization of an outgoing reply on the server or the reply operation throws an exception for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="bc63e-109">Questo argomento è basato sul [serializzazione JSON](../../../../docs/framework/wcf/samples/json-serialization.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="bc63e-109">This topic is based on the [JSON Serialization](../../../../docs/framework/wcf/samples/json-serialization.md) sample.</span></span>  
  
### <a name="to-define-the-data-contract-for-a-person"></a><span data-ttu-id="bc63e-110">Per definire il contratto dati per Person</span><span class="sxs-lookup"><span data-stu-id="bc63e-110">To define the data contract for a Person</span></span>  
  
1.  <span data-ttu-id="bc63e-111">Definire il contratto dati per `Person` collegando l'oggetto <xref:System.Runtime.Serialization.DataContractAttribute> alla classe e l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri da serializzare.</span><span class="sxs-lookup"><span data-stu-id="bc63e-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="bc63e-112">contratti dati, vedere [progettazione contratti di servizio](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="bc63e-112"> data contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
    ```  
    [DataContract]  
        internal class Person  
        {  
            [DataMember]  
            internal string name;  
  
            [DataMember]  
            internal int age;  
        }  
    ```  
  
### <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="bc63e-113">Per serializzare un'istanza di tipo Person in JSON</span><span class="sxs-lookup"><span data-stu-id="bc63e-113">To serialize an instance of type Person to JSON</span></span>  
  
1.  <span data-ttu-id="bc63e-114">Creare un'istanza del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="bc63e-114">Create an instance of the `Person` type.</span></span>  
  
    ```  
    Person p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2.  <span data-ttu-id="bc63e-115">Serializzare l'oggetto `Person` in un flusso di memoria utilizzando <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bc63e-115">Serialize the `Person` object to a memory stream using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    MemoryStream stream1 = new MemoryStream();  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3.  <span data-ttu-id="bc63e-116">Utilizzare il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> per scrivere dati JSON nel flusso.</span><span class="sxs-lookup"><span data-stu-id="bc63e-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```  
    ser.WriteObject(stream1, p);  
    ```  
  
4.  <span data-ttu-id="bc63e-117">Visualizzare l'output JSON.</span><span class="sxs-lookup"><span data-stu-id="bc63e-117">Show the JSON output.</span></span>  
  
    ```  
    stream1.Position = 0;  
    StreamReader sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
### <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="bc63e-118">Per deserializzare un'istanza di tipo Person da JSON</span><span class="sxs-lookup"><span data-stu-id="bc63e-118">To deserialize an instance of type Person from JSON</span></span>  
  
1.  <span data-ttu-id="bc63e-119">Deserializzare i dati con codifica JSON in una nuova istanza di `Person` utilizzando il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bc63e-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```  
    stream1.Position = 0;  
    Person p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2.  <span data-ttu-id="bc63e-120">Visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="bc63e-120">Show the results.</span></span>  
  
    ```  
    Console.Write("Deserialized back, got name=");  
    Console.Write(p2.name);  
    Console.Write(", age=");  
    Console.WriteLine(p2.age);  
    ```  
  
## <a name="example"></a><span data-ttu-id="bc63e-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc63e-121">Example</span></span>  
  
```  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    //Create User object.  
    User user = new User("Bob", 42);  
  
    //Create a stream to serialize the object to.  
    MemoryStream ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    User deserializedUser = new User();  
    MemoryStream ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    DataContractJsonSerializer ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="bc63e-122">Il serializzatore JSON genera un'eccezione di serializzazione per i contratti dati che dispongono di più membri con lo stesso nome, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bc63e-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
```  
[DataContract]  
public class TestDuplicateDataBase  
{  
    [DataMember]  
    public int field1 = 123;  
}  
[DataContract]  
public class TestDuplicateDataDerived : TestDuplicateDataBase  
{  
    [DataMember]  
    public new int field1 = 999;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc63e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc63e-123">See Also</span></span>  
 [<span data-ttu-id="bc63e-124">Serializzazione JSON autonoma</span><span class="sxs-lookup"><span data-stu-id="bc63e-124">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)  
 [<span data-ttu-id="bc63e-125">Supporto per JSON e altri dati formati di trasferimento</span><span class="sxs-lookup"><span data-stu-id="bc63e-125">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)
