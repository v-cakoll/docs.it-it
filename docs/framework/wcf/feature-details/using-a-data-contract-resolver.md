---
title: Uso di un resolver del contratto dati
ms.date: 03/30/2017
ms.assetid: 2e68a16c-36f0-4df4-b763-32021bff2b89
ms.openlocfilehash: 20abd4d928fc51eb359949ecbb216615e9659b7f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595024"
---
# <a name="using-a-data-contract-resolver"></a><span data-ttu-id="ac83f-102">Uso di un resolver del contratto dati</span><span class="sxs-lookup"><span data-stu-id="ac83f-102">Using a Data Contract Resolver</span></span>
<span data-ttu-id="ac83f-103">Un resolver del contratto dati consente di configurare tipi noti in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ac83f-103">A data contract resolver allows you to configure known types dynamically.</span></span> <span data-ttu-id="ac83f-104">I tipi noti sono necessari se si serializza o deserializza un tipo non previsto da un contratto dati.</span><span class="sxs-lookup"><span data-stu-id="ac83f-104">Known types are required when serializing or deserializing a type not expected by a data contract.</span></span> <span data-ttu-id="ac83f-105">Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac83f-105">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="ac83f-106">I tipi noti vengono in genere specificati in modo statico.</span><span class="sxs-lookup"><span data-stu-id="ac83f-106">Known types are normally specified statically.</span></span> <span data-ttu-id="ac83f-107">Ciò significa che è necessario conoscere tutti i tipi possibili che un'operazione può ricevere durante l'implementazione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="ac83f-107">This means you would have to know all the possible types an operation may receive while implementing the operation.</span></span> <span data-ttu-id="ac83f-108">Poiché in alcuni scenari tale condizione non è possibile, è importante specificare i tipi noti in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="ac83f-108">There are scenarios in which this is not true and being able to specify known types dynamically is important.</span></span>  
  
## <a name="creating-a-data-contract-resolver"></a><span data-ttu-id="ac83f-109">Creazione di un resolver del contratto dati</span><span class="sxs-lookup"><span data-stu-id="ac83f-109">Creating a Data Contract Resolver</span></span>  
 <span data-ttu-id="ac83f-110">La creazione di un resolver del contratto dati prevede l'implementazione di due metodi, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> e <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac83f-110">Creating a data contract resolver involves implementing two methods, <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> and <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A>.</span></span> <span data-ttu-id="ac83f-111">Questi due metodi implementano callback utilizzati rispettivamente durante la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="ac83f-111">These two methods implement callbacks that are used during serialization and deserialization, respectively.</span></span> <span data-ttu-id="ac83f-112">Il metodo <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> viene richiamato durante la serializzazione, utilizza un tipo di contratto dati e ne esegue il mapping a un nome e a uno spazio dei nomi `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="ac83f-112">The <xref:System.Runtime.Serialization.DataContractResolver.TryResolveType%2A> method is invoked during serialization and takes a data contract type and maps it to an `xsi:type` name and namespace.</span></span> <span data-ttu-id="ac83f-113">Il metodo <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> viene richiamato durante la deserializzazione, utilizza un nome e uno spazio dei nomi `xsi:type` e lo risolve in un tipo di contratto dati.</span><span class="sxs-lookup"><span data-stu-id="ac83f-113">The <xref:System.Runtime.Serialization.DataContractResolver.ResolveName%2A> method is invoked during deserialization and takes an `xsi:type` name and namespace and resolves it to a data contract type.</span></span> <span data-ttu-id="ac83f-114">Entrambi questi metodi dispongono di un parametro `knownTypeResolver` che può essere impiegato per utilizzare il resolver del tipo noto predefinito nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="ac83f-114">Both of these methods have a `knownTypeResolver` parameter that can be used to use the default known type resolver in your implementation.</span></span>  
  
 <span data-ttu-id="ac83f-115">Nell'esempio seguente viene mostrato come implementare un <xref:System.Runtime.Serialization.DataContractResolver> con cui eseguire il mapping con un tipo di contratto dati denominato `Customer` derivato da un tipo di contratto dati `Person`.</span><span class="sxs-lookup"><span data-stu-id="ac83f-115">The following example shows how to implement a <xref:System.Runtime.Serialization.DataContractResolver> to map to and from a data contract type named `Customer` derived from a data contract type `Person`.</span></span>  
  
```csharp  
public class MyCustomerResolver : DataContractResolver  
{  
    public override bool TryResolveType(Type dataContractType, Type declaredType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        if (dataContractType == typeof(Customer))  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add("SomeCustomer");  
            typeNamespace = dictionary.Add("http://tempuri.com");  
            return true;  
        }  
        else  
        {  
            return knownTypeResolver.TryResolveType(dataContractType, declaredType, null, out typeName, out typeNamespace);  
        }  
    }  
  
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        if (typeName == "SomeCustomer" && typeNamespace == "http://tempuri.com")  
        {  
            return typeof(Customer);  
        }  
        else  
        {  
            return knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ac83f-116">Una volta definito un <xref:System.Runtime.Serialization.DataContractResolver>, è possibile utilizzarlo passandolo al costruttore <xref:System.Runtime.Serialization.DataContractSerializer>, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac83f-116">Once you have defined a <xref:System.Runtime.Serialization.DataContractResolver> you can use it by passing it to the <xref:System.Runtime.Serialization.DataContractSerializer> constructor as shown in the following example.</span></span>  
  
```csharp
XmlObjectSerializer serializer = new DataContractSerializer(typeof(Customer), null, Int32.MaxValue, false, false, null, new MyCustomerResolver());  
```  
  
 <span data-ttu-id="ac83f-117">È possibile specificare un <xref:System.Runtime.Serialization.DataContractResolver> in una chiamata ai metodi <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> o <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType>, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac83f-117">You can specify a <xref:System.Runtime.Serialization.DataContractResolver> in a call to the <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A?displayProperty=nameWithType> or <xref:System.Runtime.Serialization.DataContractSerializer.WriteObject%2A?displayProperty=nameWithType> methods, as shown in the following example.</span></span>  
  
```csharp
MemoryStream ms = new MemoryStream();  
DataContractSerializer serializer = new DataContractSerializer(typeof(Customer));  
XmlDictionaryWriter writer = XmlDictionaryWriter.CreateDictionaryWriter(XmlWriter.Create(ms));  
serializer.WriteObject(writer, new Customer(), new MyCustomerResolver());  
writer.Flush();  
ms.Position = 0;  
Console.WriteLine(((Customer)serializer.ReadObject(XmlDictionaryReader.CreateDictionaryReader(XmlReader.Create(ms)), false, new MyCustomerResolver()));  
```  
  
 <span data-ttu-id="ac83f-118">È in alternativa possibile impostarlo su <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, come indicato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ac83f-118">Or you can set it on the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> as shown in the following example.</span></span>  
  
```csharp
ServiceHost host = new ServiceHost(typeof(MyService));  
  
ContractDescription cd = host.Description.Endpoints[0].Contract;  
OperationDescription myOperationDescription = cd.Operations.Find("Echo");  
  
DataContractSerializerOperationBehavior serializerBehavior = myOperationDescription.Behaviors.Find<DataContractSerializerOperationBehavior>();  
if (serializerBehavior == null)  
{  
    serializerBehavior = new DataContractSerializerOperationBehavior(myOperationDescription);  
    myOperationDescription.Behaviors.Add(serializerBehavior);  
}  
  
SerializerBehavior.DataContractResolver = new MyCustomerResolver();  
```  
  
 <span data-ttu-id="ac83f-119">È possibile specificare in modo dichiarativo un resolver del contratto dati implementando un attributo che possa essere applicato a un servizio.</span><span class="sxs-lookup"><span data-stu-id="ac83f-119">You can declaratively specify a data contract resolver by implementing an attribute that can be applied to a service.</span></span>  <span data-ttu-id="ac83f-120">Per ulteriori informazioni, vedere l'esempio [KnownAssemblyAttribute](../samples/knownassemblyattribute.md) .</span><span class="sxs-lookup"><span data-stu-id="ac83f-120">For more information, see the [KnownAssemblyAttribute](../samples/knownassemblyattribute.md) sample.</span></span> <span data-ttu-id="ac83f-121">Questo esempio implementa un attributo denominato "KnownAssembly" che aggiunge un resolver del contratto dati personalizzato al comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="ac83f-121">This sample implements an attribute called "KnownAssembly" that adds a custom data contract resolver to the service’s behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac83f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac83f-122">See also</span></span>

- [<span data-ttu-id="ac83f-123">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="ac83f-123">Data Contract Known Types</span></span>](data-contract-known-types.md)
- [<span data-ttu-id="ac83f-124">Esempio di DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="ac83f-124">DataContractSerializer Sample</span></span>](../samples/datacontractserializer-sample.md)
- [<span data-ttu-id="ac83f-125">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="ac83f-125">KnownAssemblyAttribute</span></span>](../samples/knownassemblyattribute.md)
