---
title: DataContractResolver
ms.date: 03/30/2017
ms.assetid: 6c200c02-bc14-4b8d-bbab-9da31185b805
ms.openlocfilehash: 716bcb2bb43656051beffb15da9c7a988942ecd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183789"
---
# <a name="datacontractresolver"></a><span data-ttu-id="604a4-102">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="604a4-102">DataContractResolver</span></span>
<span data-ttu-id="604a4-103">In questo esempio viene illustrato come personalizzare i processi di serializzazione e deserializzazione tramite la classe <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="604a4-103">This sample demonstrates how the serialization and deserialization processes can be customized by using the <xref:System.Runtime.Serialization.DataContractResolver> class.</span></span> <span data-ttu-id="604a4-104">Nell'esempio viene descritto come utilizzare un oggetto DataContractResolver per eseguire il mapping dei tipi CLR a una rappresentazione xsi:type e dalla stessa durante la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="604a4-104">This sample shows how to use a DataContractResolver to map CLR types to and from an xsi:type representation during serialization and deserialization.</span></span>

## <a name="sample-details"></a><span data-ttu-id="604a4-105">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="604a4-105">Sample Details</span></span>
 <span data-ttu-id="604a4-106">Nell'esempio vengono definiti i tipi CLR seguenti.</span><span class="sxs-lookup"><span data-stu-id="604a4-106">The sample defines the following CLR types.</span></span>

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

 <span data-ttu-id="604a4-107">Nell'esempio viene caricato l'assembly e viene estratto ognuno di questi tipi. Viene quindi eseguita la serializzazione e la deserializzazione dei tipi.</span><span class="sxs-lookup"><span data-stu-id="604a4-107">The sample loads the assembly, extracts each of these types, and then serializes and deserializes them.</span></span> <span data-ttu-id="604a4-108">L'oggetto <xref:System.Runtime.Serialization.DataContractResolver> viene collegato al processo di serializzazione passando un'istanza della classe derivata da <xref:System.Runtime.Serialization.DataContractResolver> al costruttore <xref:System.Runtime.Serialization.DataContractSerializer>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="604a4-108">The <xref:System.Runtime.Serialization.DataContractResolver> is plugged into the serialization process by passing an instance of the <xref:System.Runtime.Serialization.DataContractResolver>-derived class to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, as shown in the following example.</span></span>

```csharp
this.serializer = new DataContractSerializer(typeof(Object), null, int.MaxValue, false, true, null, new MyDataContractResolver(assembly));
```

 <span data-ttu-id="604a4-109">Nell'esempio vengono quindi serializzati i tipi CLR, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="604a4-109">The sample then serializes the CLR types as shown in the following code example.</span></span>

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

 <span data-ttu-id="604a4-110">Nell'esempio vengono quindi deserializzati gli oggetto xsi:type, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="604a4-110">The sample then deserializes the xsi:types as shown in the following code example.</span></span>

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

 <span data-ttu-id="604a4-111">Poiché al costruttore <xref:System.Runtime.Serialization.DataContractResolver> viene passato l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> personalizzato, durante la serializzazione viene chiamato il metodo <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> per eseguire il mapping di un tipo CLR a un oggetto `xsi:type` equivalente.</span><span class="sxs-lookup"><span data-stu-id="604a4-111">Since the custom <xref:System.Runtime.Serialization.DataContractResolver> is passed in to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor, the <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> is called during serialization to map a CLR type to an equivalent `xsi:type`.</span></span> <span data-ttu-id="604a4-112">Analogamente, durante la deserializzazione viene chiamato il metodo <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> per eseguire il mapping dell'oggetto `xsi:type` a un tipo CLR equivalente.</span><span class="sxs-lookup"><span data-stu-id="604a4-112">Similarly the <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> is called during deserialization to map the `xsi:type` to an equivalent CLR type.</span></span> <span data-ttu-id="604a4-113">In questo esempio, l'oggetto <xref:System.Runtime.Serialization.DataContractResolver> viene definito come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="604a4-113">In this sample, the <xref:System.Runtime.Serialization.DataContractResolver> is defined as shown in the following example.</span></span>

 <span data-ttu-id="604a4-114">L'esempio di codice riportato di seguito è una classe che deriva da <xref:System.Runtime.Serialization.DataContractResolver>.</span><span class="sxs-lookup"><span data-stu-id="604a4-114">The following code example is a class deriving from <xref:System.Runtime.Serialization.DataContractResolver>.</span></span>

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

 <span data-ttu-id="604a4-115">Come parte dell'esempio, il progetto Types genera l'assembly con tutti i tipi utilizzati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="604a4-115">As part of the sample, the Types project generates the assembly with all the types that are used in this sample.</span></span> <span data-ttu-id="604a4-116">Utilizzare il progetto per aggiungere, rimuovere o modificare i tipi che saranno serializzati.</span><span class="sxs-lookup"><span data-stu-id="604a4-116">Use this project to add, remove or modify the types that will be serialized.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="604a4-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="604a4-117">To use this sample</span></span>

1. <span data-ttu-id="604a4-118">Utilizzando Visual Studio 2012, aprire il file di soluzione DCRSample.sln.</span><span class="sxs-lookup"><span data-stu-id="604a4-118">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="604a4-119">Per eseguire la soluzione, premere F5</span><span class="sxs-lookup"><span data-stu-id="604a4-119">To run the solution, press F5</span></span>

> [!IMPORTANT]
> <span data-ttu-id="604a4-120">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="604a4-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="604a4-121">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="604a4-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="604a4-122">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="604a4-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="604a4-123">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="604a4-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractResolver`  
  
## <a name="see-also"></a><span data-ttu-id="604a4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="604a4-124">See also</span></span>

- [<span data-ttu-id="604a4-125">Uso di un resolver del contratto dati</span><span class="sxs-lookup"><span data-stu-id="604a4-125">Using a Data Contract Resolver</span></span>](../../../../docs/framework/wcf/feature-details/using-a-data-contract-resolver.md)
