---
title: Serializzazione e metadati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3dea98a381bf468182f24dff27af50e46ad38ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="f777b-102">Serializzazione e metadati</span><span class="sxs-lookup"><span data-stu-id="f777b-102">Serialization and Metadata</span></span>
<span data-ttu-id="f777b-103">Se l'applicazione serializza e deserializza oggetti, potrebbe essere necessario aggiungere voci al file di direttive di runtime (rd.xml) per assicurarsi che i metadati necessari siano presenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f777b-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="f777b-104">Esistono due categorie di serializzatori e ciascuna richiede una gestione differente nel file di direttive di runtime:</span><span class="sxs-lookup"><span data-stu-id="f777b-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
-   <span data-ttu-id="f777b-105">Serializzatori di terze parti basati su reflection.</span><span class="sxs-lookup"><span data-stu-id="f777b-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="f777b-106">Richiedono modifiche al file di direttive di runtime e sono descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="f777b-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
-   <span data-ttu-id="f777b-107">Serializzatori non basati su reflection, presenti nella libreria di classi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f777b-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="f777b-108">Possono richiedere modifiche al file di direttive di runtime e sono descritti nella sezione [Serializzatori Microsoft](#Microsoft).</span><span class="sxs-lookup"><span data-stu-id="f777b-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="f777b-109">Serializzatori di terze parti</span><span class="sxs-lookup"><span data-stu-id="f777b-109">Third-party serializers</span></span>  
 <span data-ttu-id="f777b-110">I serializzatori di terze parti, incluso Newtonsoft.JSON, sono in genere basati su reflection.</span><span class="sxs-lookup"><span data-stu-id="f777b-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="f777b-111">Dato un oggetto binario di grandi dimensioni (BLOB) di dati serializzati, i campi dati vengono assegnati a un tipo concreto cercando i campi del tipo di destinazione per nome.</span><span class="sxs-lookup"><span data-stu-id="f777b-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="f777b-112">Come minimo, l'uso di queste librerie causa eccezioni [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) per ogni oggetto <xref:System.Type> che si prova a serializzare o deserializzare in una raccolta `List<Type>`.</span><span class="sxs-lookup"><span data-stu-id="f777b-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="f777b-113">Il modo più semplice per risolvere i problemi causati da metadati mancanti per questi serializzatori è raccogliere i tipi che verranno usati nella serializzazione in un singolo spazio dei nomi (ad esempio `App.Models`) e applicarvi una direttiva metadati `Serialize`:</span><span class="sxs-lookup"><span data-stu-id="f777b-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="f777b-114">Per informazioni sulla sintassi usata in questo esempio, vedere [Elemento \<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="f777b-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="f777b-115">Serializzatori Microsoft</span><span class="sxs-lookup"><span data-stu-id="f777b-115">Microsoft serializers</span></span>  
 <span data-ttu-id="f777b-116">Nonostante le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Xml.Serialization.XmlSerializer> non si basino sulla reflection, richiedono che il codice venga generato in base all'oggetto da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="f777b-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="f777b-117">I costruttori di overload per ciascun serializzatore includono un parametro <xref:System.Type> che specifica il tipo da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="f777b-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="f777b-118">Il modo in cui si specifica che il tipo nel codice definisce l'azione che l'utente deve accettare, come illustrato nelle due sezioni.</span><span class="sxs-lookup"><span data-stu-id="f777b-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="f777b-119">typeof usato nel costruttore</span><span class="sxs-lookup"><span data-stu-id="f777b-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="f777b-120">Se si chiama un costruttore di queste classi di serializzazione e si include la parola chiave [typeof](~/docs/csharp/language-reference/keywords/typeof.md) di C# nella chiamata al metodo, **non è necessario effettuare operazioni aggiuntive**.</span><span class="sxs-lookup"><span data-stu-id="f777b-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="f777b-121">Ad esempio, in ognuna delle seguenti chiamate a un costruttore di classe di serializzazione, la parola chiave `typeof` viene usata come parte dell'espressione passata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="f777b-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="f777b-122">Il compilatore [!INCLUDE[net_native](../../../includes/net-native-md.md)] gestirà automaticamente questo codice.</span><span class="sxs-lookup"><span data-stu-id="f777b-122">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="f777b-123">typeof usato fuori dal costruttore</span><span class="sxs-lookup"><span data-stu-id="f777b-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="f777b-124">Se si chiama un costruttore di queste classi di serializzazione e si usa la parola chiave [typeof](~/docs/csharp/language-reference/keywords/typeof.md) di C# fuori dall'espressione fornita al parametro <xref:System.Type> del costruttore, come nel codice seguente, il compilatore di [!INCLUDE[net_native](../../../includes/net-native-md.md)] non può risolvere il tipo:</span><span class="sxs-lookup"><span data-stu-id="f777b-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="f777b-125">In questo caso, è necessario specificare il tipo nel file di direttive di runtime con l'aggiunta di una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f777b-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="f777b-126">Analogamente, se si chiama un costruttore come <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> e si fornisce una matrice di oggetti <xref:System.Type> aggiuntivi da serializzare, come nel codice seguente, il compilatore di [!INCLUDE[net_native](../../../includes/net-native-md.md)] non riesce a risolvere questi tipi.</span><span class="sxs-lookup"><span data-stu-id="f777b-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="f777b-127">È necessario aggiungere come quelle riportate di seguito per ogni tipo al file di direttive del runtime:</span><span class="sxs-lookup"><span data-stu-id="f777b-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="f777b-128">Per informazioni sulla sintassi usata in questo esempio, vedere [Elemento \<Type>](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="f777b-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f777b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f777b-129">See Also</span></span>  
 [<span data-ttu-id="f777b-130">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="f777b-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="f777b-131">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="f777b-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [<span data-ttu-id="f777b-132">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="f777b-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)  
 [<span data-ttu-id="f777b-133">Elemento \<Namespace></span><span class="sxs-lookup"><span data-stu-id="f777b-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
