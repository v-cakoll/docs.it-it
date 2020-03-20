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
# <a name="interoperable-object-references"></a>Riferimenti a oggetti interoperabili
Per impostazione predefinita, <xref:System.Runtime.Serialization.DataContractSerializer> serializza gli oggetti per valore. È possibile <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> utilizzare la proprietà per indicare al serializzatore del contratto dati di mantenere i riferimenti agli oggetti durante la serializzazione degli oggetti.  
  
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
  
 Tuttavia, <xref:System.Runtime.Serialization.XsdDataContractExporter> non descrive `id` `ref` gli attributi e nel `preserveObjectReferences` relativo schema, anche quando la proprietà è impostata su `true`.  
  
## <a name="using-isreference"></a>Uso di IsReference  
 Per generare informazioni di riferimento all'oggetto valide in <xref:System.Runtime.Serialization.DataContractAttribute> base allo schema che <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> le `true`descrive, applicare l'attributo a un tipo e impostare il flag su . L'esempio seguente modifica `X` la classe nell'esempio precedente aggiungendo `IsReference`:  
  
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
  
 L'utilizzo di `IsReference` garantisce conformità nelle sequenze di andata e ritorno dei messaggi. Senza di esso, quando un tipo viene generato dallo schema, l'output XML per tale tipo non è necessariamente compatibile con lo schema originariamente assunto. In altre parole, nonostante la serializzazione degli attributi `id` e `ref`, lo schema originale avrebbe potuto impedire a tali attributi (o a tutti gli attributi) di verificarsi nell'XML. Con `IsReference` applicato a un membro dati, il membro continua a essere riconosciuto come a cui è *possibile fare riferimento* quando è stato eseguito il round ingritto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference?displayProperty=nameWithType>
