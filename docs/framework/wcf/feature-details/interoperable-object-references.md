---
title: Riferimenti a oggetti interoperativi
ms.date: 04/15/2019
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: ada9084f6ac3c97dc641571c0cb8379a2fac68a8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610639"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="f68da-102">Riferimenti a oggetti interoperativi</span><span class="sxs-lookup"><span data-stu-id="f68da-102">Interoperable object references</span></span>
<span data-ttu-id="f68da-103">Per impostazione predefinita, <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore.</span><span class="sxs-lookup"><span data-stu-id="f68da-103">By default, <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="f68da-104">È possibile usare il <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> proprietà per indicare il serializzatore dei contratti dati per mantenere i riferimenti all'oggetto durante la serializzazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="f68da-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the data contract serializer to preserve object references when serializing objects.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="f68da-105">XML generato</span><span class="sxs-lookup"><span data-stu-id="f68da-105">Generated XML</span></span>  
 <span data-ttu-id="f68da-106">Si consideri, come esempio, l'oggetto seguente:</span><span class="sxs-lookup"><span data-stu-id="f68da-106">As an example, consider the following object:</span></span>  
  
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
  
 <span data-ttu-id="f68da-107">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `false` (impostazione predefinita), viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="f68da-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="f68da-108">Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `true`, viene generato l'XML seguente:</span><span class="sxs-lookup"><span data-stu-id="f68da-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 <span data-ttu-id="f68da-109">Tuttavia <xref:System.Runtime.Serialization.XsdDataContractExporter> non viene descritto il `id` e `ref` attributi nello schema, anche quando il `preserveObjectReferences` viene impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="f68da-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> doesn't describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="f68da-110">Uso di IsReference</span><span class="sxs-lookup"><span data-stu-id="f68da-110">Using IsReference</span></span>  
 <span data-ttu-id="f68da-111">Per generare informazioni di riferimento oggetto valide secondo lo schema che lo descrive, applicare il <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo di attributo e impostare il <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag `true`.</span><span class="sxs-lookup"><span data-stu-id="f68da-111">To generate object reference information that's valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="f68da-112">L'esempio seguente modifica classi `X` nell'esempio precedente aggiungendo `IsReference`:</span><span class="sxs-lookup"><span data-stu-id="f68da-112">The following example modifies class `X` in the previous example by adding `IsReference`:</span></span>  
  
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

 <span data-ttu-id="f68da-113">L'XML generato è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f68da-113">The generated XML is as follows:</span></span>  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 <span data-ttu-id="f68da-114">L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f68da-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="f68da-115">In caso contrario, quando viene generato un tipo di schema, l'output XML di che tipo non è necessariamente compatibile con lo schema inizialmente presupposto.</span><span class="sxs-lookup"><span data-stu-id="f68da-115">Without it, when a type is generated from schema, the XML output for that type isn't necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="f68da-116">In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML.</span><span class="sxs-lookup"><span data-stu-id="f68da-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="f68da-117">Con `IsReference` applicato a un membro dati, il membro continua a essere riconosciuti come *referenziabile* quando round trip.</span><span class="sxs-lookup"><span data-stu-id="f68da-117">With `IsReference` applied to a data member, the member continues to be recognized as *referenceable* when round-tripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68da-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f68da-118">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
