---
title: API basate sulla reflection
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 1d8daceb6b744b984f86b011ad7952d0da583a79
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181083"
---
# <a name="apis-that-rely-on-reflection"></a><span data-ttu-id="fe0c4-102">API basate sulla reflection</span><span class="sxs-lookup"><span data-stu-id="fe0c4-102">APIs That Rely on Reflection</span></span>
<span data-ttu-id="fe0c4-103">In alcuni casi, l'uso della reflection nel codice non è ovvio, quindi la catena di strumenti .NET Native non mantiene i metadati necessari in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-103">In some cases, the use of reflection in code isn't obvious, and so the .NET Native tool chain doesn't preserve metadata that is needed at run time.</span></span> <span data-ttu-id="fe0c4-104">In questo argomento vengono illustrati modelli di programmazione o API comuni non considerati parte dell'API di reflection ma basati sulla reflection per una corretta esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-104">This topic covers some common APIs or common programming patterns that aren't considered part of the reflection API but that rely on reflection to execute successfully.</span></span> <span data-ttu-id="fe0c4-105">Se vengono usati nel codice sorgente, è possibile aggiungere informazioni su di essi al file di direttive di runtime (.rd.xml) in modo che le chiamate a queste API non generino un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md) o altre eccezioni al runtime.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-105">If you use them in your source code, you can add information about them to the runtime directives (.rd.xml) file so that calls to these APIs do not throw a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception or some other exception at run time.</span></span>  
  
## <a name="typemakegenerictype-method"></a><span data-ttu-id="fe0c4-106">Metodo Type.MakeGenericType</span><span class="sxs-lookup"><span data-stu-id="fe0c4-106">Type.MakeGenericType method</span></span>  
 <span data-ttu-id="fe0c4-107">È possibile creare dinamicamente un'istanza di un tipo generico `AppClass<T>` chiamando il metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> usando un codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-107">You can dynamically instantiate a generic type `AppClass<T>` by calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 <span data-ttu-id="fe0c4-108">Per una corretta esecuzione del codice al runtime, sono necessari diversi elementi di metadati.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-108">For this code to succeed at run time, several items of metadata are required.</span></span> <span data-ttu-id="fe0c4-109">Prima di tutto, sono richiesti metadati `Browse` per il tipo generico privo di istanze, `AppClass<T>`:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-109">The first is `Browse` metadata for the uninstantiated generic type, `AppClass<T>`:</span></span>  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="fe0c4-110">Questo assicura l'esito positivo della chiamata al metodo <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> e la restituzione di un oggetto <xref:System.Type> valido.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-110">This allows the <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> method call to succeed and return a valid <xref:System.Type> object.</span></span>  
  
 <span data-ttu-id="fe0c4-111">Tuttavia, anche se si aggiungono i metadati per il tipo generico privo di istanze, la chiamata al metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> genera un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md):</span><span class="sxs-lookup"><span data-stu-id="fe0c4-111">But even when you add metadata for the uninstantiated generic type, calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method throws a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception:</span></span>  
  
<span data-ttu-id="fe0c4-112">Non è possibile eseguire questa operazione perché i metadati per il tipo seguente sono stati rimossi per motivi di prestazioni:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-112">This operation cannot be carried out as metadata for the following type was removed for performance reasons:</span></span>  
  
<span data-ttu-id="fe0c4-113">`App1.AppClass`1<System. Int32>'.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-113">`App1.AppClass`1<System.Int32>\`.</span></span>  
  
 <span data-ttu-id="fe0c4-114">È possibile aggiungere la seguente direttiva di runtime al file di direttive di runtime per aggiungere i metadati `Activate` per la specifica creazione di un'istanza in `AppClass<T>` di <xref:System.Int32?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-114">You can add the following run-time directive to the runtime directives file to add `Activate` metadata for the specific instantiation over `AppClass<T>` of <xref:System.Int32?displayProperty=nameWithType>:</span></span>  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 <span data-ttu-id="fe0c4-115">Le singole creazioni di istanze in `AppClass<T>` richiedono direttive separate se vengono create con il metodo <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> e non vengono usate staticamente.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-115">Each different instantiation over `AppClass<T>` requires a separate directive if it is being created with the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method and not used statically.</span></span>  
  
## <a name="methodinfomakegenericmethod-method"></a><span data-ttu-id="fe0c4-116">Metodo MethodInfo.MakeGenericMethod</span><span class="sxs-lookup"><span data-stu-id="fe0c4-116">MethodInfo.MakeGenericMethod method</span></span>  
 <span data-ttu-id="fe0c4-117">In una classe `Class1` con un metodo generico `GetMethod<T>(T t)`, `GetMethod` può essere richiamato mediante reflection usando un codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-117">Given a class `Class1` with a generic method `GetMethod<T>(T t)`, `GetMethod` can be invoked through reflection by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 <span data-ttu-id="fe0c4-118">Per una corretta esecuzione, questo codice richiede diversi elementi di metadati:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-118">To run successfully, this code requires several items of metadata:</span></span>  
  
- <span data-ttu-id="fe0c4-119">I metadati `Browse` per il tipo di metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-119">`Browse` metadata for the type whose method you want to call.</span></span>  
  
- <span data-ttu-id="fe0c4-120">I metadati `Browse` per il metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-120">`Browse` metadata for the method you want to call.</span></span>  <span data-ttu-id="fe0c4-121">Se si tratta di un metodo pubblico, l'aggiunta di metadati `Browse` pubblici per il tipo contenitore include anche il metodo.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-121">If it is a public method, adding public `Browse` metadata for the containing type includes the method, too.</span></span>  
  
- <span data-ttu-id="fe0c4-122">Metadati dinamici per il metodo che si vuole chiamare, in modo che il delegato della chiamata di reflection non venga rimosso dalla catena di strumenti .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-122">Dynamic metadata for the method you want to call, so that the reflection invocation delegate is not removed by the .NET Native tool chain.</span></span> <span data-ttu-id="fe0c4-123">Se i metadati dinamici non sono disponibili per il metodo, viene generata la seguente eccezione quando viene chiamato il metodo <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-123">If dynamic metadata is missing for the method, the following exception is thrown when the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> method is called:</span></span>  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 <span data-ttu-id="fe0c4-124">Le seguenti direttive di runtime assicurano la disponibilità di tutti i metadati necessari:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-124">The following runtime directives ensure that all required metadata is available:</span></span>  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 <span data-ttu-id="fe0c4-125">È necessaria una direttiva `MethodInstantiation` per ogni singola creazione di un'istanza del metodo richiamato dinamicamente; l'elemento `Arguments` viene aggiornato per riflettere ogni singolo argomento di creazione di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-125">A `MethodInstantiation` directive is required for each different instantiation of the method that is dynamically invoked, and the `Arguments` element is updated to reflect each different instantiation argument.</span></span>  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a><span data-ttu-id="fe0c4-126">Metodi Array.CreateInstance e Type.MakeTypeArray</span><span class="sxs-lookup"><span data-stu-id="fe0c4-126">Array.CreateInstance and Type.MakeTypeArray methods</span></span>  
 <span data-ttu-id="fe0c4-127">Il seguente esempio chiama i metodi <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> e <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> in un tipo `Class1`.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-127">The following example calls the <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> methods on a type, `Class1`.</span></span>  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 <span data-ttu-id="fe0c4-128">Se non sono presenti i metadati della matrice, si verificano i seguenti errori:</span><span class="sxs-lookup"><span data-stu-id="fe0c4-128">If no array metadata is present, the following error results:</span></span>  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 <span data-ttu-id="fe0c4-129">I metadati `Browse` per il tipo di matrice sono richiesti per la creazione dinamica di un'istanza.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-129">`Browse` metadata for the array type is required to dynamically instantiate it.</span></span>  <span data-ttu-id="fe0c4-130">La seguente direttiva di runtime consente la creazione dinamica di un'istanza di `Class1[]`.</span><span class="sxs-lookup"><span data-stu-id="fe0c4-130">The following runtime directive allows dynamic instantiation of `Class1[]`.</span></span>  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe0c4-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fe0c4-131">See also</span></span>

- [<span data-ttu-id="fe0c4-132">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="fe0c4-132">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="fe0c4-133">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="fe0c4-133">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
