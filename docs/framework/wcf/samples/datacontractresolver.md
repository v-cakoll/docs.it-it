---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: c2a2afaa450e9abe17b62f6be07a2dc41459ca20
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600023"
---
# <a name="datacontractresolver"></a>DataContractResolver
In questo esempio viene illustrato come personalizzare i processi di serializzazione e deserializzazione tramite la classe <xref:System.Runtime.Serialization.DataContractResolver>. Nell'esempio viene descritto come utilizzare un oggetto DataContractResolver per eseguire il mapping dei tipi CLR a una rappresentazione xsi:type e dalla stessa durante la serializzazione e la deserializzazione.

## <a name="sample-details"></a>Dettagli dell'esempio
 Nell'esempio vengono definiti i tipi CLR seguenti.

```csharp
using System;
using System.Runtime.Serialization;

namespace Types
{
    [DataContract]
    public class Customer
    {
        [DataMember]
        public string Name { get; set; }
    }

    [DataContract]
    public class VIPCustomer : Customer
    {
        [DataMember]
        public string VipInfo { get; set; }
    }

    [DataContract]
    public class RegularCustomer : Customer
    {
    }

    [DataContract]
    public class PreferredVIPCustomer : VIPCustomer
    {
    }
}
```

 Nell'esempio viene caricato l'assembly e viene estratto ognuno di questi tipi. Viene quindi eseguita la serializzazione e la deserializzazione dei tipi. L'oggetto <xref:System.Runtime.Serialization.DataContractResolver> viene collegato al processo di serializzazione passando un'istanza della classe derivata da <xref:System.Runtime.Serialization.DataContractResolver> al costruttore <xref:System.Runtime.Serialization.DataContractSerializer>, come illustrato nell'esempio seguente.

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 Nell'esempio vengono quindi serializzati i tipi CLR, come illustrato nell'esempio di codice seguente.

```csharp
Assembly assembly = Assembly.Load(new AssemblyName("Types"));

public void serialize(Type type)
{
    Object instance = Activator.CreateInstance(type);

    Console.WriteLine("----------------------------------------");
    Console.WriteLine();
    Console.WriteLine("Serializing type: {0}", type.Name);
    Console.WriteLine();
    this.buffer = new StringBuilder();
    using (XmlWriter xmlWriter = XmlWriter.Create(this.buffer))
    {
        try
        {
            this.serializer.WriteObject(xmlWriter, instance);
        }
        catch (SerializationException error)
        {
            Console.WriteLine(error.ToString());
        }
    }
    Console.WriteLine(this.buffer.ToString());
}
```

 Nell'esempio vengono quindi deserializzati gli oggetto xsi:type, come illustrato nell'esempio di codice seguente.

```csharp
public void deserialize(Type type)
{
    Console.WriteLine();
    Console.WriteLine("Deserializing type: {0}", type.Name);
    Console.WriteLine();
    using (XmlReader xmlReader = XmlReader.Create(new StringReader(this.buffer.ToString())))
    {
        Object obj = this.serializer.ReadObject(xmlReader);
    }
}
```

 Poiché al costruttore <xref:System.Runtime.Serialization.DataContractResolver> viene passato l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> personalizzato, durante la serializzazione viene chiamato il metodo <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> per eseguire il mapping di un tipo CLR a un oggetto `xsi:type` equivalente. Analogamente, durante la deserializzazione viene chiamato il metodo <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> per eseguire il mapping dell'oggetto `xsi:type` a un tipo CLR equivalente. In questo esempio, l'oggetto <xref:System.Runtime.Serialization.DataContractResolver> viene definito come illustrato nell'esempio seguente.

 L'esempio di codice riportato di seguito è una classe che deriva da <xref:System.Runtime.Serialization.DataContractResolver>.

```csharp
class MyDataContractResolver : DataContractResolver
{
    private Dictionary<string, XmlDictionaryString> dictionary = new Dictionary<string, XmlDictionaryString>();
    Assembly assembly;

    public MyDataContractResolver(Assembly assembly)
    {
        this.assembly = assembly;
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        XmlDictionaryString tName;
        XmlDictionaryString tNamespace;
        if (dictionary.TryGetValue(typeName, out tName) && dictionary.TryGetValue(typeNamespace, out tNamespace))
        {
            return this.assembly.GetType(tNamespace.Value + "." + tName.Value);
        }
        else
        {
            return null;
        }
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        string name = dataContractType.Name;
        string namesp = dataContractType.Namespace;
        typeName = new XmlDictionaryString(XmlDictionary.Empty, name, 0);
        typeNamespace = new XmlDictionaryString(XmlDictionary.Empty, namesp, 0);
        if (!dictionary.ContainsKey(dataContractType.Name))
        {
            dictionary.Add(name, typeName);
        }
        if (!dictionary.ContainsKey(dataContractType.Namespace))
        {
            dictionary.Add(namesp, typeNamespace);
        }
    }
}
```

 Come parte dell'esempio, il progetto Types genera l'assembly con tutti i tipi utilizzati in questo esempio. Utilizzare il progetto per aggiungere, rimuovere o modificare i tipi che saranno serializzati.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2012 aprire il file della soluzione DCRSample. sln.

2. Per eseguire la soluzione, premere F5

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un resolver del contratto dati](../feature-details/using-a-data-contract-resolver.md)
