---
title: Serializzazione di base
ms.date: 03/30/2017
helpviewer_keywords:
- binary serialization, basic serialization
- serialization, basic serialization
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
dev_langs:
- CSharp
ms.openlocfilehash: ce86f7897c5c117c4fd6f1eabc4c8b802103261c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248030"
---
# <a name="basic-serialization"></a>Serializzazione di base

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Il modo più semplice per rendere serializzabile una classe è contrassegnarla con l'attributo <xref:System.SerializableAttribute>, come illustrato di seguito.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
L'esempio di codice seguente illustra come è possibile serializzare un'istanza della classe in un file.  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
In questo esempio viene utilizzato un formattatore binario per eseguire la serializzazione. È sufficiente creare un'istanza del flusso e il formattatore che si vuole usare e quindi chiamare il metodo **Serialize** sul formattatore. Il flusso e l'oggetto da serializzare vengono forniti a questa chiamata come parametri. Sebbene non sia stato dimostrato in modo esplicito in questo esempio, verranno serializzate tutte le variabili del membro di una classe, anche quelle contrassegnate come private. Da questo punto di vista, la serializzazione binaria differisce dalla classe <xref:System.Xml.Serialization.XmlSerializer>, che serializza solo campi pubblici. Per informazioni sull'esclusione di variabili membro dalla serializzazione binaria, vedere [Selezione selettiva](selective-serialization.md).  
  
Il ripristino dell'oggetto allo stato antecedente risulta molto semplice. Per prima cosa, creare un flusso per la lettura e un oggetto <xref:System.Runtime.Serialization.Formatter> e quindi istruire il formattatore in modo che deserializzi l'oggetto. Nell'esempio di codice riportato di seguito viene illustrato come fare.  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
La classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> usata in precedenza è molto efficiente e produce un flusso di byte compatto. Tutti gli oggetti serializzati con questo formattatore possono inoltre essere deserializzati con lo stesso formattatore, rendendolo uno strumento ideale per la serializzazione di oggetti che saranno deserializzati su .NET Framework. È importante notare che i costruttori non vengono chiamati quando un oggetto viene deserializzato. Questo vincolo è posizionato sulla deserializzazione per motivi di prestazioni. Tuttavia, in tal modo vengono violati alcuni dei normali contratti stabiliti tra il runtime e il writer dell'oggetto e gli sviluppatori devono essere certi di comprendere le ramificazioni quando contrassegnano un oggetto come serializzabile.  
  
Se la portabilità è un requisito, usare invece <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. È sufficiente sostituire **BinaryFormatter** nel codice sopra riportato con **SoapFormatter** e quindi chiamare **Serialize** e **Deserialize**, come nel caso precedente. Questo formattatore produce il seguente output per l'esempio utilizzato in precedenza.  
  
```xml  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
È importante tenere presente che l'attributo [Serializable](xref:System.SerializableAttribute) non può essere ereditato. Se una nuova classe viene derivata da `MyObject`, tale classe deve anche essere contrassegnata con l'attributo; in caso contrario non sarà possibile serializzarla. Se, ad esempio, si tenta di serializzare un'istanza della classe seguente, si riceve un'eccezione <xref:System.Runtime.Serialization.SerializationException> in cui si specifica che il tipo `MyStuff` non è contrassegnato come serializzabile.  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 Benché utile, l'utilizzo dell'attributo [Serializable](xref:System.SerializableAttribute) presenta alcune limitazioni, come dimostrato in precedenza. Fare riferimento alle [Linee guida relative alla serializzazione](serialization-guidelines.md) per informazioni sul momento in cui è opportuno contrassegnare una classe per la serializzazione. La serializzazione non può essere aggiunta a una classe dopo essere stata compilata.  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione binaria](binary-serialization.md)
- [Serializzazione SOAP e XML](xml-and-soap-serialization.md)
