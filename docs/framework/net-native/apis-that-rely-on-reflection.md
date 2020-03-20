---
title: API basate sulla reflection
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 1d8daceb6b744b984f86b011ad7952d0da583a79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181083"
---
# <a name="apis-that-rely-on-reflection"></a>API basate sulla reflection
In alcuni casi, l'uso della reflection nel codice non è ovvio e pertanto la catena di strumenti .NET Native non mantiene i metadati necessari in fase di esecuzione. In questo argomento vengono illustrati modelli di programmazione o API comuni non considerati parte dell'API di reflection ma basati sulla reflection per una corretta esecuzione. Se vengono usati nel codice sorgente, è possibile aggiungere informazioni su di essi al file di direttive di runtime (.rd.xml) in modo che le chiamate a queste API non generino un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md) o altre eccezioni al runtime.  
  
## <a name="typemakegenerictype-method"></a>Metodo Type.MakeGenericType  
 È possibile creare dinamicamente un'istanza di un tipo generico `AppClass<T>` chiamando il metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> usando un codice simile al seguente:  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 Per una corretta esecuzione del codice al runtime, sono necessari diversi elementi di metadati. Prima di tutto, sono richiesti metadati `Browse` per il tipo generico privo di istanze, `AppClass<T>`:  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 Questo assicura l'esito positivo della chiamata al metodo <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> e la restituzione di un oggetto <xref:System.Type> valido.  
  
 Tuttavia, anche se si aggiungono i metadati per il tipo generico privo di istanze, la chiamata al metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> genera un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md):  
  
Questa operazione non può essere eseguita come metadati per il tipo seguente è stata rimossa per motivi di prestazioni:This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
`App1.AppClass`1<>System.Int32 '.  
  
 È possibile aggiungere la seguente direttiva di runtime al file di direttive di runtime per aggiungere i metadati `Activate` per la specifica creazione di un'istanza in `AppClass<T>` di <xref:System.Int32?displayProperty=nameWithType>:  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 Le singole creazioni di istanze in `AppClass<T>` richiedono direttive separate se vengono create con il metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> e non vengono usate staticamente.  
  
## <a name="methodinfomakegenericmethod-method"></a>Metodo MethodInfo.MakeGenericMethod  
 In una classe `Class1` con un metodo generico `GetMethod<T>(T t)`, `GetMethod` può essere richiamato mediante reflection usando un codice simile al seguente:  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 Per una corretta esecuzione, questo codice richiede diversi elementi di metadati:  
  
- I metadati `Browse` per il tipo di metodo da chiamare.  
  
- I metadati `Browse` per il metodo da chiamare.  Se si tratta di un metodo pubblico, l'aggiunta di metadati `Browse` pubblici per il tipo contenitore include anche il metodo.  
  
- Metadati dinamici per il metodo che si desidera chiamare, in modo che il delegato di chiamata di reflection non viene rimosso dalla catena di strumenti .NET Native. Se i metadati dinamici non sono disponibili per il metodo, viene generata la seguente eccezione quando viene chiamato il metodo <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>:  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 Le seguenti direttive di runtime assicurano la disponibilità di tutti i metadati necessari:  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 È necessaria una direttiva `MethodInstantiation` per ogni singola creazione di un'istanza del metodo richiamato dinamicamente; l'elemento `Arguments` viene aggiornato per riflettere ogni singolo argomento di creazione di un'istanza.  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a>Metodi Array.CreateInstance e Type.MakeTypeArray  
 Il seguente esempio chiama i metodi <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> e <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> in un tipo `Class1`.  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 Se non sono presenti i metadati della matrice, si verificano i seguenti errori:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 I metadati `Browse` per il tipo di matrice sono richiesti per la creazione dinamica di un'istanza.  La seguente direttiva di runtime consente la creazione dinamica di un'istanza di `Class1[]`.  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a>Vedere anche

- [Guida introduttiva](getting-started-with-net-native.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
