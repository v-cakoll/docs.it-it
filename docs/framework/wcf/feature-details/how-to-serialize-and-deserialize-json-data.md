---
title: 'Procedura: Serializzare e deserializzare dati JSON'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 0bebdbb3d74d58db093c4ec1e0e88138c7080335
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947901"
---
# <a name="how-to-serialize-and-deserialize-json-data"></a><span data-ttu-id="8c30c-102">Procedura: Serializzare e deserializzare i dati JSON</span><span class="sxs-lookup"><span data-stu-id="8c30c-102">How to: Serialize and deserialize JSON data</span></span>
<span data-ttu-id="8c30c-103">JSON (JavaScript Object Notation) è un efficiente formato di codifica dati che consente scambi rapidi di piccole quantità di dati tra browser client e servizi Web compatibili con AJAX.</span><span class="sxs-lookup"><span data-stu-id="8c30c-103">JSON (JavaScript Object Notation) is an efficient data encoding format that enables fast exchanges of small amounts of data between client browsers and AJAX-enabled Web services.</span></span>  
  
 <span data-ttu-id="8c30c-104">Questo articolo illustra come serializzare oggetti di tipo .NET in dati con codifica JSON e quindi deserializzare i dati in formato JSON in istanze di tipi .NET.</span><span class="sxs-lookup"><span data-stu-id="8c30c-104">This article demonstrates how to serialize .NET type objects into JSON-encoded data and then deserialize data in the JSON format back into instances of .NET types.</span></span> <span data-ttu-id="8c30c-105">In questo esempio viene utilizzato un contratto dati per illustrare la serializzazione e la deserializzazione di un <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>tipo definito `Person` dall'utente e viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8c30c-105">This example uses a data contract to demonstrate serialization and deserialization of a user-defined `Person` type and uses <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
 <span data-ttu-id="8c30c-106">In genere, la serializzazione e la deserializzazione JSON vengono gestite automaticamente da Windows Communication Foundation (WCF) quando si usano i tipi di contratto dati nelle operazioni del servizio esposte su endpoint abilitati per AJAX.</span><span class="sxs-lookup"><span data-stu-id="8c30c-106">Normally, JSON serialization and deserialization are handled automatically by Windows Communication Foundation (WCF) when you use data contract types in service operations that are exposed over AJAX-enabled endpoints.</span></span> <span data-ttu-id="8c30c-107">In alcuni casi, tuttavia, potrebbe essere necessario lavorare direttamente con i dati JSON.</span><span class="sxs-lookup"><span data-stu-id="8c30c-107">However, in some cases you may need to work with JSON data directly.</span></span>   
  
> [!NOTE]
> <span data-ttu-id="8c30c-108">Se si verifica un errore durante la serializzazione di una risposta in uscita nel server o per qualche altro motivo, è possibile che non venga restituito al client come errore.</span><span class="sxs-lookup"><span data-stu-id="8c30c-108">If an error occurs during serialization of an outgoing reply on the server or for some other reason, it may not get returned to the client as a fault.</span></span>  
  
 <span data-ttu-id="8c30c-109">Questo articolo è basato sull'esempio di [serializzazione JSON](../samples/json-serialization.md) .</span><span class="sxs-lookup"><span data-stu-id="8c30c-109">This article is based on the [JSON serialization](../samples/json-serialization.md) sample.</span></span>  
  
## <a name="to-define-the-data-contract-for-a-person-type"></a><span data-ttu-id="8c30c-110">Per definire il contratto dati per un tipo Person</span><span class="sxs-lookup"><span data-stu-id="8c30c-110">To define the data contract for a Person type</span></span> 
  
1. <span data-ttu-id="8c30c-111">Definire il contratto dati per `Person` collegando l'oggetto <xref:System.Runtime.Serialization.DataContractAttribute> alla classe e l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri da serializzare.</span><span class="sxs-lookup"><span data-stu-id="8c30c-111">Define the data contract for `Person` by attaching the <xref:System.Runtime.Serialization.DataContractAttribute> to the class and <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the members you want to serialize.</span></span> <span data-ttu-id="8c30c-112">Per ulteriori informazioni sui contratti dati, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="8c30c-112">For more information about data contracts, see [Designing service contracts](../designing-service-contracts.md).</span></span>  
  
    ```csharp  
    [DataContract]  
    internal class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
    ```  
  
## <a name="to-serialize-an-instance-of-type-person-to-json"></a><span data-ttu-id="8c30c-113">Per serializzare un'istanza di tipo Person in JSON</span><span class="sxs-lookup"><span data-stu-id="8c30c-113">To serialize an instance of type Person to JSON</span></span>  
  
1. <span data-ttu-id="8c30c-114">Creare un'istanza del tipo `Person`.</span><span class="sxs-lookup"><span data-stu-id="8c30c-114">Create an instance of the `Person` type.</span></span>  
  
    ```csharp  
    var p = new Person();  
    p.name = "John";  
    p.age = 42;  
    ```  
  
2. <span data-ttu-id="8c30c-115">Serializzare `Person` l'oggetto in un flusso di memoria <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>usando.</span><span class="sxs-lookup"><span data-stu-id="8c30c-115">Serialize the `Person` object to a memory stream by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    var stream1 = new MemoryStream();  
    var ser = new DataContractJsonSerializer(typeof(Person));  
    ```  
  
3. <span data-ttu-id="8c30c-116">Utilizzare il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> per scrivere dati JSON nel flusso.</span><span class="sxs-lookup"><span data-stu-id="8c30c-116">Use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> method to write JSON data to the stream.</span></span>  
  
    ```csharp  
    ser.WriteObject(stream1, p);  
    ```  
  
4. <span data-ttu-id="8c30c-117">Visualizzare l'output JSON.</span><span class="sxs-lookup"><span data-stu-id="8c30c-117">Show the JSON output.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    var sr = new StreamReader(stream1);  
    Console.Write("JSON form of Person object: ");  
    Console.WriteLine(sr.ReadToEnd());  
    ```  
  
## <a name="to-deserialize-an-instance-of-type-person-from-json"></a><span data-ttu-id="8c30c-118">Per deserializzare un'istanza di tipo Person da JSON</span><span class="sxs-lookup"><span data-stu-id="8c30c-118">To deserialize an instance of type Person from JSON</span></span>  
  
1. <span data-ttu-id="8c30c-119">Deserializzare i dati con codifica JSON in una nuova istanza di `Person` utilizzando il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8c30c-119">Deserialize the JSON-encoded data into a new instance of `Person` by using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> method of the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
    ```csharp  
    stream1.Position = 0;  
    var p2 = (Person)ser.ReadObject(stream1);  
    ```  
  
2. <span data-ttu-id="8c30c-120">Visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8c30c-120">Show the results.</span></span>  
  
    ```csharp  
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");  
    ```  
  
## <a name="example"></a><span data-ttu-id="8c30c-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c30c-121">Example</span></span>  
  
```csharp  
// Create a User object and serialize it to a JSON stream.  
public static string WriteFromObject()  
{  
    // Create User object.  
    var user = new User("Bob", 42);  
  
    // Create a stream to serialize the object to.  
    var ms = new MemoryStream();  
  
    // Serializer the User object to the stream.  
    var ser = new DataContractJsonSerializer(typeof(User));  
    ser.WriteObject(ms, user);  
    byte[] json = ms.ToArray();  
    ms.Close();  
    return Encoding.UTF8.GetString(json, 0, json.Length);  
}  
  
// Deserialize a JSON stream to a User object.  
public static User ReadToObject(string json)  
{  
    var deserializedUser = new User();  
    var ms = new MemoryStream(Encoding.UTF8.GetBytes(json));  
    var ser = new DataContractJsonSerializer(deserializedUser.GetType());  
    deserializedUser = ser.ReadObject(ms) as User;  
    ms.Close();  
    return deserializedUser;  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="8c30c-122">Il serializzatore JSON genera un'eccezione di serializzazione per i contratti dati che dispongono di più membri con lo stesso nome, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8c30c-122">The JSON serializer throws a serialization exception for data contracts that have multiple members with the same name, as shown in the following sample code.</span></span>  
  
```csharp  
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
  
## <a name="see-also"></a><span data-ttu-id="8c30c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c30c-123">See also</span></span>

- [<span data-ttu-id="8c30c-124">Serializzazione JSON autonoma</span><span class="sxs-lookup"><span data-stu-id="8c30c-124">Stand-alone JSON serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="8c30c-125">Supporto per JSON e altri formati di trasferimento dati</span><span class="sxs-lookup"><span data-stu-id="8c30c-125">Support for JSON and other data transfer formats</span></span>](support-for-json-and-other-data-transfer-formats.md)
