---
title: Serializzazione e metadati
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: cc9adf0e6627ef3190e74fea5d4f0f3afd581811
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389223"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="c1301-102">Serializzazione e metadati</span><span class="sxs-lookup"><span data-stu-id="c1301-102">Serialization and Metadata</span></span>

<span data-ttu-id="c1301-103">Se l'applicazione serializza e deserializza oggetti, potrebbe essere necessario aggiungere voci al file di direttive di runtime (rd.xml) per assicurarsi che i metadati necessari siano presenti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c1301-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="c1301-104">Esistono due categorie di serializzatori e ciascuna richiede una gestione differente nel file di direttive di runtime:</span><span class="sxs-lookup"><span data-stu-id="c1301-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
- <span data-ttu-id="c1301-105">Serializzatori di terze parti basati su reflection.</span><span class="sxs-lookup"><span data-stu-id="c1301-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="c1301-106">Richiedono modifiche al file di direttive di runtime e sono descritti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c1301-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
- <span data-ttu-id="c1301-107">Serializzatori non basati su reflection trovati nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1301-107">Non-reflection-based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="c1301-108">Possono richiedere modifiche al file di direttive di runtime e sono descritti nella sezione [Serializzatori Microsoft](#Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c1301-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>
## <a name="third-party-serializers"></a><span data-ttu-id="c1301-109">Serializzatori di terze parti</span><span class="sxs-lookup"><span data-stu-id="c1301-109">Third-party serializers</span></span>

 <span data-ttu-id="c1301-110">I serializzatori di terze parti, incluso Newtonsoft.JSON, sono in genere basati su reflection.</span><span class="sxs-lookup"><span data-stu-id="c1301-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="c1301-111">Dato un oggetto binario di grandi dimensioni (BLOB) di dati serializzati, i campi dati vengono assegnati a un tipo concreto cercando i campi del tipo di destinazione per nome.</span><span class="sxs-lookup"><span data-stu-id="c1301-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="c1301-112">Come minimo, l'uso di queste librerie causa eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) per ogni oggetto <xref:System.Type> che si prova a serializzare o deserializzare in una raccolta `List<Type>`.</span><span class="sxs-lookup"><span data-stu-id="c1301-112">At a minimum, using these libraries causes [MissingMetadataException](missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="c1301-113">Il modo più semplice per risolvere i problemi causati da metadati mancanti per questi serializzatori è raccogliere i tipi che verranno usati nella serializzazione in un singolo spazio dei nomi (ad esempio `App.Models`) e applicarvi una direttiva metadati `Serialize`:</span><span class="sxs-lookup"><span data-stu-id="c1301-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="c1301-114">Per informazioni sulla sintassi utilizzata [ \<](namespace-element-net-native.md)nell'esempio, vedere Elemento> dello spazio dei nomi .</span><span class="sxs-lookup"><span data-stu-id="c1301-114">For information about the syntax used in the example, see [\<Namespace> Element](namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>
## <a name="microsoft-serializers"></a><span data-ttu-id="c1301-115">Serializzatori Microsoft</span><span class="sxs-lookup"><span data-stu-id="c1301-115">Microsoft serializers</span></span>

 <span data-ttu-id="c1301-116">Nonostante le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e <xref:System.Xml.Serialization.XmlSerializer> non si basino sulla reflection, richiedono che il codice venga generato in base all'oggetto da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="c1301-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="c1301-117">I costruttori di overload per ciascun serializzatore includono un parametro <xref:System.Type> che specifica il tipo da serializzare o deserializzare.</span><span class="sxs-lookup"><span data-stu-id="c1301-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="c1301-118">Il modo in cui si specifica che il tipo nel codice definisce l'azione che l'utente deve accettare, come illustrato nelle due sezioni.</span><span class="sxs-lookup"><span data-stu-id="c1301-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="c1301-119">typeof usato nel costruttore</span><span class="sxs-lookup"><span data-stu-id="c1301-119">typeof used in the constructor</span></span>

 <span data-ttu-id="c1301-120">Se si chiama un costruttore di queste classi di serializzazione e si include l'operatore [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) di C, **non è necessario eseguire alcuna operazione aggiuntiva.**</span><span class="sxs-lookup"><span data-stu-id="c1301-120">If you call a constructor of these serialization classes and include the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="c1301-121">Ad esempio, in ognuna delle seguenti chiamate a un costruttore di classe di serializzazione, la parola chiave `typeof` viene usata come parte dell'espressione passata al costruttore.</span><span class="sxs-lookup"><span data-stu-id="c1301-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="c1301-122">Il compilatore nativo di .NET gestirà automaticamente questo codice.</span><span class="sxs-lookup"><span data-stu-id="c1301-122">The .NET Native compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="c1301-123">typeof usato fuori dal costruttore</span><span class="sxs-lookup"><span data-stu-id="c1301-123">typeof used outside the constructor</span></span>

 <span data-ttu-id="c1301-124">Se si chiama un costruttore di queste classi di serializzazione e si utilizza <xref:System.Type> l'operatore [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) di C' all'esterno dell'espressione fornita al parametro del costruttore, come nel codice seguente, il compilatore nativo di .NET non è in grado di risolvere il tipo:</span><span class="sxs-lookup"><span data-stu-id="c1301-124">If you call a constructor of these serialization classes and use the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the .NET Native compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="c1301-125">In questo caso, è necessario specificare il tipo nel file di direttive di runtime con l'aggiunta di una voce simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c1301-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="c1301-126">Analogamente, se si chiama <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> un costruttore, <xref:System.Type> ad esempio e si fornisce una matrice di oggetti aggiuntivi da serializzare, come nel codice seguente, il compilatore nativo di .NET non è in grado di risolvere questi tipi.</span><span class="sxs-lookup"><span data-stu-id="c1301-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the .NET Native compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
<span data-ttu-id="c1301-127">Aggiungere voci come le seguenti per ogni tipo al file delle direttive di runtime:</span><span class="sxs-lookup"><span data-stu-id="c1301-127">Add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
<span data-ttu-id="c1301-128">Per informazioni sulla sintassi utilizzata [ \<](type-element-net-native.md)nell'esempio, vedere Elemento> Tipo .</span><span class="sxs-lookup"><span data-stu-id="c1301-128">For information about the syntax used in the example, see [\<Type> Element](type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1301-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1301-129">See also</span></span>

- [<span data-ttu-id="c1301-130">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c1301-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c1301-131">Elementi direttiva di runtime</span><span class="sxs-lookup"><span data-stu-id="c1301-131">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="c1301-132">\<Tipo> elemento</span><span class="sxs-lookup"><span data-stu-id="c1301-132">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="c1301-133">\<Elemento> dello spazio dei nomiNamespace> Element</span><span class="sxs-lookup"><span data-stu-id="c1301-133">\<Namespace> Element</span></span>](namespace-element-net-native.md)
