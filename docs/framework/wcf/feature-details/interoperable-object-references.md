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
# <a name="interoperable-object-references"></a>Riferimenti a oggetti interoperativi
Per impostazione predefinita, <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore. È possibile usare il <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> proprietà per indicare il serializzatore dei contratti dati per mantenere i riferimenti all'oggetto durante la serializzazione di oggetti.  
  
## <a name="generated-xml"></a>XML generato  
 Si consideri, come esempio, l'oggetto seguente:  
  
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
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `false` (impostazione predefinita), viene generato l'XML seguente:  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 Con <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> impostato su `true`, viene generato l'XML seguente:  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1"></B>  
</X>  
```  
  
 Tuttavia <xref:System.Runtime.Serialization.XsdDataContractExporter> non viene descritto il `id` e `ref` attributi nello schema, anche quando il `preserveObjectReferences` viene impostata su `true`.  
  
## <a name="using-isreference"></a>Uso di IsReference  
 Per generare informazioni di riferimento oggetto valide secondo lo schema che lo descrive, applicare il <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo di attributo e impostare il <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag `true`. L'esempio seguente modifica classi `X` nell'esempio precedente aggiungendo `IsReference`:  
  
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

 L'XML generato è il seguente:  

```xml
<X>  
    <A id="1">
        <Value>contents of A</Value>  
    </A> 
    <B ref="1"></B>  
</X>
```  
  
 L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi. In caso contrario, quando viene generato un tipo di schema, l'output XML di che tipo non è necessariamente compatibile con lo schema inizialmente presupposto. In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML. Con `IsReference` applicato a un membro dati, il membro continua a essere riconosciuti come *referenziabile* quando round trip.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
