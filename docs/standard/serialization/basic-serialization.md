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
# <a name="basic-serialization"></a><span data-ttu-id="0b649-102">Serializzazione di base</span><span class="sxs-lookup"><span data-stu-id="0b649-102">Basic serialization</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="0b649-103">Il modo più semplice per rendere serializzabile una classe è contrassegnarla con l'attributo <xref:System.SerializableAttribute>, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0b649-103">The easiest way to make a class serializable is to mark it with the <xref:System.SerializableAttribute> as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
<span data-ttu-id="0b649-104">L'esempio di codice seguente illustra come è possibile serializzare un'istanza della classe in un file.</span><span class="sxs-lookup"><span data-stu-id="0b649-104">The following code example shows how an instance of this class can be serialized to a file.</span></span>  
  
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
  
<span data-ttu-id="0b649-105">In questo esempio viene utilizzato un formattatore binario per eseguire la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="0b649-105">This example uses a binary formatter to do the serialization.</span></span> <span data-ttu-id="0b649-106">È sufficiente creare un'istanza del flusso e il formattatore che si vuole usare e quindi chiamare il metodo **Serialize** sul formattatore.</span><span class="sxs-lookup"><span data-stu-id="0b649-106">All you need to do is create an instance of the stream and the formatter you intend to use, and then call the **Serialize** method on the formatter.</span></span> <span data-ttu-id="0b649-107">Il flusso e l'oggetto da serializzare vengono forniti a questa chiamata come parametri.</span><span class="sxs-lookup"><span data-stu-id="0b649-107">The stream and the object to serialize are provided as parameters to this call.</span></span> <span data-ttu-id="0b649-108">Sebbene non sia stato dimostrato in modo esplicito in questo esempio, verranno serializzate tutte le variabili del membro di una classe, anche quelle contrassegnate come private.</span><span class="sxs-lookup"><span data-stu-id="0b649-108">Although it is not explicitly demonstrated in this example, all member variables of a class will be serialized—even variables marked as private.</span></span> <span data-ttu-id="0b649-109">Da questo punto di vista, la serializzazione binaria differisce dalla classe <xref:System.Xml.Serialization.XmlSerializer>, che serializza solo campi pubblici.</span><span class="sxs-lookup"><span data-stu-id="0b649-109">In this aspect, binary serialization differs from the <xref:System.Xml.Serialization.XmlSerializer> class, which only serializes public fields.</span></span> <span data-ttu-id="0b649-110">Per informazioni sull'esclusione di variabili membro dalla serializzazione binaria, vedere [Selezione selettiva](selective-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="0b649-110">For information on excluding member variables from binary serialization, see [Selective Serialization](selective-serialization.md).</span></span>  
  
<span data-ttu-id="0b649-111">Il ripristino dell'oggetto allo stato antecedente risulta molto semplice.</span><span class="sxs-lookup"><span data-stu-id="0b649-111">Restoring the object back to its former state is just as easy.</span></span> <span data-ttu-id="0b649-112">Per prima cosa, creare un flusso per la lettura e un oggetto <xref:System.Runtime.Serialization.Formatter> e quindi istruire il formattatore in modo che deserializzi l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0b649-112">First, create a stream for reading and a <xref:System.Runtime.Serialization.Formatter>, and then instruct the formatter to deserialize the object.</span></span> <span data-ttu-id="0b649-113">Nell'esempio di codice riportato di seguito viene illustrato come fare.</span><span class="sxs-lookup"><span data-stu-id="0b649-113">The code example below shows how this is done.</span></span>  
  
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
  
<span data-ttu-id="0b649-114">La classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> usata in precedenza è molto efficiente e produce un flusso di byte compatto.</span><span class="sxs-lookup"><span data-stu-id="0b649-114">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> used above is very efficient and produces a compact byte stream.</span></span> <span data-ttu-id="0b649-115">Tutti gli oggetti serializzati con questo formattatore possono inoltre essere deserializzati con lo stesso formattatore, rendendolo uno strumento ideale per la serializzazione di oggetti che saranno deserializzati su .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0b649-115">All objects serialized with this formatter can also be deserialized with it, which makes it an ideal tool for serializing objects that will be deserialized on the .NET Framework.</span></span> <span data-ttu-id="0b649-116">È importante notare che i costruttori non vengono chiamati quando un oggetto viene deserializzato.</span><span class="sxs-lookup"><span data-stu-id="0b649-116">It is important to note that constructors are not called when an object is deserialized.</span></span> <span data-ttu-id="0b649-117">Questo vincolo è posizionato sulla deserializzazione per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0b649-117">This constraint is placed on deserialization for performance reasons.</span></span> <span data-ttu-id="0b649-118">Tuttavia, in tal modo vengono violati alcuni dei normali contratti stabiliti tra il runtime e il writer dell'oggetto e gli sviluppatori devono essere certi di comprendere le ramificazioni quando contrassegnano un oggetto come serializzabile.</span><span class="sxs-lookup"><span data-stu-id="0b649-118">However, this violates some of the usual contracts the runtime makes with the object writer, and developers should ensure that they understand the ramifications when marking an object as serializable.</span></span>  
  
<span data-ttu-id="0b649-119">Se la portabilità è un requisito, usare invece <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="0b649-119">If portability is a requirement, use the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> instead.</span></span> <span data-ttu-id="0b649-120">È sufficiente sostituire **BinaryFormatter** nel codice sopra riportato con **SoapFormatter** e quindi chiamare **Serialize** e **Deserialize**, come nel caso precedente.</span><span class="sxs-lookup"><span data-stu-id="0b649-120">Simply replace the **BinaryFormatter** in the code above with **SoapFormatter,** and call **Serialize** and **Deserialize** as before.</span></span> <span data-ttu-id="0b649-121">Questo formattatore produce il seguente output per l'esempio utilizzato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0b649-121">This formatter produces the following output for the example used above.</span></span>  
  
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
  
<span data-ttu-id="0b649-122">È importante tenere presente che l'attributo [Serializable](xref:System.SerializableAttribute) non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="0b649-122">It's important to note that the [Serializable](xref:System.SerializableAttribute) attribute cannot be inherited.</span></span> <span data-ttu-id="0b649-123">Se una nuova classe viene derivata da `MyObject`, tale classe deve anche essere contrassegnata con l'attributo; in caso contrario non sarà possibile serializzarla.</span><span class="sxs-lookup"><span data-stu-id="0b649-123">If you derive a new class from `MyObject`, the new class must be marked with the attribute as well, or it cannot be serialized.</span></span> <span data-ttu-id="0b649-124">Se, ad esempio, si tenta di serializzare un'istanza della classe seguente, si riceve un'eccezione <xref:System.Runtime.Serialization.SerializationException> in cui si specifica che il tipo `MyStuff` non è contrassegnato come serializzabile.</span><span class="sxs-lookup"><span data-stu-id="0b649-124">For example, when you attempt to serialize an instance of the class below, you'll get a <xref:System.Runtime.Serialization.SerializationException> informing you that the `MyStuff` type is not marked as serializable.</span></span>  
  
```csharp  
public class MyStuff : MyObject
{  
  public int n3;  
}  
```  
  
 <span data-ttu-id="0b649-125">Benché utile, l'utilizzo dell'attributo [Serializable](xref:System.SerializableAttribute) presenta alcune limitazioni, come dimostrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0b649-125">Using the [Serializable](xref:System.SerializableAttribute) attribute is convenient, but it has limitations as previously demonstrated.</span></span> <span data-ttu-id="0b649-126">Fare riferimento alle [Linee guida relative alla serializzazione](serialization-guidelines.md) per informazioni sul momento in cui è opportuno contrassegnare una classe per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="0b649-126">Refer to the [Serialization Guidelines](serialization-guidelines.md) for information about when you should mark a class for serialization.</span></span> <span data-ttu-id="0b649-127">La serializzazione non può essere aggiunta a una classe dopo essere stata compilata.</span><span class="sxs-lookup"><span data-stu-id="0b649-127">Serialization cannot be added to a class after it has been compiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b649-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0b649-128">See also</span></span>

- [<span data-ttu-id="0b649-129">Serializzazione binaria</span><span class="sxs-lookup"><span data-stu-id="0b649-129">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="0b649-130">Serializzazione SOAP e XML</span><span class="sxs-lookup"><span data-stu-id="0b649-130">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
