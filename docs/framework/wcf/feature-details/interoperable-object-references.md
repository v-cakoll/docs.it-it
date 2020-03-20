---
title: Riferimenti a oggetti interoperabili
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 0927f217a1666f8f27ca9c3e68f80a96b9c0f2b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184698"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="e0262-102">Riferimenti a oggetti interoperabili</span><span class="sxs-lookup"><span data-stu-id="e0262-102">Interoperable object references</span></span>
<span data-ttu-id="e0262-103">Per impostazione predefinita, <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore.</span><span class="sxs-lookup"><span data-stu-id="e0262-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="e0262-104">È possibile <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> utilizzare la proprietà per indicare al serializzatore del contratto dati di mantenere i riferimenti agli oggetti durante la serializzazione degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e0262-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="e0262-105">XML generato</span><span class="sxs-lookup"><span data-stu-id="e0262-105">Generated XML</span></span>  
 <span data-ttu-id="e0262-106">Si consideri, come esempio, l'oggetto seguente:</span><span class="sxs-lookup"><span data-stu-id="e0262-106">As an example, consider the following object:</span></span>  
  
```csharp  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass
{  
}  
```  
  
 <span data-ttu-id="e0262-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `false` (impostazione predefinita), viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="e0262-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="e0262-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `true`, viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="e0262-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="e0262-109">Tuttavia, <xref:System.Runtime.Serialization.XsdDataContractExporter> non descrive `id` `ref` gli attributi e nel `preserveObjectReferences` relativo schema, anche quando la proprietà è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="e0262-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="e0262-110">Uso di IsReference</span><span class="sxs-lookup"><span data-stu-id="e0262-110">Using IsReference</span></span>  
 <span data-ttu-id="e0262-111">Per generare informazioni di riferimento all'oggetto valide in <xref:System.Runtime.Serialization.DataContractAttribute> base allo schema che <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> le `true`descrive, applicare l'attributo a un tipo e impostare il flag su .</span><span class="sxs-lookup"><span data-stu-id="e0262-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="e0262-112">L'esempio seguente modifica `X` la classe nell'esempio precedente aggiungendo `IsReference`:</span><span class="sxs-lookup"><span data-stu-id="e0262-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
```csharp
[DataContract(IsReference=true)]
public class X
{  
     SomeClass someInstance = new SomeClass();
     [DataMember]
     public SomeClass A = someInstance;
     [DataMember]
     public SomeClass B = someInstance;
}
  
public class SomeClass
{
}  
````

 <span data-ttu-id="e0262-113">L'XML generato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e0262-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A>
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="e0262-114">L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="e0262-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="e0262-115">Senza di esso, quando un tipo viene generato dallo schema, l'output XML per tale tipo non è necessariamente compatibile con lo schema originariamente assunto.</span><span class="sxs-lookup"><span data-stu-id="e0262-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="e0262-116">In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML.</span><span class="sxs-lookup"><span data-stu-id="e0262-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="e0262-117">Con `IsReference` applicato a un membro dati, il membro continua a essere riconosciuto come a cui è *possibile fare riferimento* quando è stato eseguito il round ingritto.</span><span class="sxs-lookup"><span data-stu-id="e0262-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0262-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0262-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
