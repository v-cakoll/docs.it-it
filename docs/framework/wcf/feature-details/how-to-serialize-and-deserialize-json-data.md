---
title: 'Procedura: utilizzare DataContractJsonSerializer'
ms.date: 03/25/2019
ms.assetid: 88abc1fb-8196-4ee3-a23b-c6934144d1dd
ms.openlocfilehash: 3cf8cc52587a64e7273ab9e0de0b1751d00827cf
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901220"
---
# <a name="how-to-use-datacontractjsonserializer"></a>Come utilizzare DataContractJsonSerializer

> [!NOTE]
> Questo articolo riguarda <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>. Per la maggior parte degli scenari che coinvolgono la serializzazione e la deserializzazione di JSON, è consigliabile usare le API nello [spazio dei nomi System. Text. JSON](../../../standard/serialization/system-text-json-overview.md).

JSON (JavaScript Object Notation) è un efficiente formato di codifica dati che consente scambi rapidi di piccole quantità di dati tra browser client e servizi Web compatibili con AJAX.

Questo articolo illustra come serializzare oggetti di tipo .NET in dati con codifica JSON e quindi deserializzare i dati in formato JSON in istanze di tipi .NET. In questo esempio viene utilizzato un contratto dati per illustrare la serializzazione e la deserializzazione di un tipo di `Person` definito dall'utente e viene utilizzato <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

In genere, la serializzazione e la deserializzazione JSON vengono gestite automaticamente da Windows Communication Foundation (WCF) quando si usano i tipi di contratto dati nelle operazioni del servizio esposte su endpoint abilitati per AJAX. In alcuni casi, tuttavia, potrebbe essere necessario lavorare direttamente con i dati JSON.

Questo articolo è basato sull' [esempio DataContractJsonSerializer](../samples/json-serialization.md).

## <a name="to-define-the-data-contract-for-a-person-type"></a>Per definire il contratto dati per un tipo Person

1. Definire il contratto dati per `Person` collegando l'oggetto <xref:System.Runtime.Serialization.DataContractAttribute> alla classe e l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> ai membri da serializzare. Per ulteriori informazioni sui contratti dati, vedere [progettazione di contratti di servizio](../designing-service-contracts.md).

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

## <a name="to-serialize-an-instance-of-type-person-to-json"></a>Per serializzare un'istanza di tipo Person in JSON

> [!NOTE]
> Se si verifica un errore durante la serializzazione di una risposta in uscita nel server o per qualche altro motivo, è possibile che non venga restituito al client come errore.

1. Creare un'istanza del tipo `Person`.

    ```csharp
    var p = new Person();
    p.name = "John";
    p.age = 42;
    ```

2. Serializzare l'oggetto `Person` in un flusso di memoria utilizzando l'<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

    ```csharp
    var stream1 = new MemoryStream();
    var ser = new DataContractJsonSerializer(typeof(Person));
    ```

3. Utilizzare il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> per scrivere dati JSON nel flusso.

    ```csharp
    ser.WriteObject(stream1, p);
    ```

4. Visualizzare l'output JSON.

    ```csharp
    stream1.Position = 0;
    var sr = new StreamReader(stream1);
    Console.Write("JSON form of Person object: ");
    Console.WriteLine(sr.ReadToEnd());
    ```

## <a name="to-deserialize-an-instance-of-type-person-from-json"></a>Per deserializzare un'istanza di tipo Person da JSON

1. Deserializzare i dati con codifica JSON in una nuova istanza di `Person` utilizzando il metodo <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject%2A> di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

    ```csharp
    stream1.Position = 0;
    var p2 = (Person)ser.ReadObject(stream1);
    ```

2. Visualizzare i risultati.

    ```csharp
    Console.WriteLine($"Deserialized back, got name={p2.name}, age={p2.age}");
    ```

## <a name="example"></a>Esempio

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
> Il serializzatore JSON genera un'eccezione di serializzazione per i contratti dati che dispongono di più membri con lo stesso nome, come illustrato nel codice di esempio seguente.

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

## <a name="see-also"></a>Vedere anche

- [Serializzazione JSON in .NET](../../../standard/serialization/system-text-json-overview.md)
