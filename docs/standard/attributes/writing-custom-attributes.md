---
title: Scrittura di attributi personalizzati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d3fb814d6b458de90d684a3ac92e22a62e290a9a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="writing-custom-attributes"></a><span data-ttu-id="9e591-102">Scrittura di attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="9e591-102">Writing Custom Attributes</span></span>
<span data-ttu-id="9e591-103">Per progettare attributi personalizzati, non è necessario apprendere molti nuovi concetti.</span><span class="sxs-lookup"><span data-stu-id="9e591-103">To design your own custom attributes, you do not need to master many new concepts.</span></span> <span data-ttu-id="9e591-104">Se si ha familiarità con la programmazione orientata agli oggetti e si è in grado di progettare le classi, si ha già gran parte delle conoscenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="9e591-104">If you are familiar with object-oriented programming and know how to design classes, you already have most of the knowledge needed.</span></span> <span data-ttu-id="9e591-105">Gli attributi personalizzati sono essenzialmente classi tradizionali che derivano direttamente o indirettamente da <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9e591-105">Custom attributes are essentially traditional classes that derive directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9e591-106">Analogamente alle classi tradizionali, gli attributi personalizzati contengono metodi che archiviano e recuperano dati.</span><span class="sxs-lookup"><span data-stu-id="9e591-106">Just like traditional classes, custom attributes contain methods that store and retrieve data.</span></span>  
  
 <span data-ttu-id="9e591-107">I passaggi fondamentali per progettare classi di attributi personalizzati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e591-107">The primary steps to properly design custom attribute classes are as follows:</span></span>  
  
-   [<span data-ttu-id="9e591-108">Applicazione di AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="9e591-108">Applying the AttributeUsageAttribute</span></span>](#cpconapplyingattributeusageattribute)  
  
-   [<span data-ttu-id="9e591-109">Dichiarazione della classe di attributi</span><span class="sxs-lookup"><span data-stu-id="9e591-109">Declaring the attribute class</span></span>](#cpcondeclaringattributeclass)  
  
-   [<span data-ttu-id="9e591-110">Dichiarazione dei costruttori</span><span class="sxs-lookup"><span data-stu-id="9e591-110">Declaring constructors</span></span>](#cpcondeclaringconstructors)  
  
-   [<span data-ttu-id="9e591-111">Dichiarazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9e591-111">Declaring properties</span></span>](#cpcondeclaringproperties)  
  
 <span data-ttu-id="9e591-112">Questa sezione illustra ognuno di questi passaggi e termina con [esempio di attributo personalizzato](#cpconcustomattributeexample).</span><span class="sxs-lookup"><span data-stu-id="9e591-112">This section describes each of these steps and concludes with a [custom attribute example](#cpconcustomattributeexample).</span></span>  
  
<a name="cpconapplyingattributeusageattribute"></a>   
## <a name="applying-the-attributeusageattribute"></a><span data-ttu-id="9e591-113">Applicazione di AttributeUsageAttribute</span><span class="sxs-lookup"><span data-stu-id="9e591-113">Applying the AttributeUsageAttribute</span></span>  
 <span data-ttu-id="9e591-114">La dichiarazione di attributo personalizzato inizia con **AttributeUsageAttribute**, che definisce alcune delle caratteristiche chiave della classe di attributi.</span><span class="sxs-lookup"><span data-stu-id="9e591-114">A custom attribute declaration begins with the **AttributeUsageAttribute**, which defines some of the key characteristics of your attribute class.</span></span> <span data-ttu-id="9e591-115">Ad esempio, è possibile specificare se l'attributo può essere ereditato da altre classi o gli elementi a cui può essere applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-115">For example, you can specify whether your attribute can be inherited by other classes or specify which elements the attribute can be applied to.</span></span> <span data-ttu-id="9e591-116">Il frammento di codice seguente illustra come specificare **AttributeUsageAttribute**.</span><span class="sxs-lookup"><span data-stu-id="9e591-116">The following code fragment demonstrates how to use the **AttributeUsageAttribute**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <span data-ttu-id="9e591-117">L'oggetto <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> ha tre membri importanti per la creazione di attributi personalizzati: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2)e [AllowMultiple](#cpconwritingcustomattributesanchor3).</span><span class="sxs-lookup"><span data-stu-id="9e591-117">The <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> has three members that are important for the creation of custom attributes: [AttributeTargets](#cpconwritingcustomattributesanchor1), [Inherited](#cpconwritingcustomattributesanchor2), and [AllowMultiple](#cpconwritingcustomattributesanchor3).</span></span>  
  
<a name="cpconwritingcustomattributesanchor1"></a>   
### <a name="attributetargets-member"></a><span data-ttu-id="9e591-118">Membro AttributeTargets</span><span class="sxs-lookup"><span data-stu-id="9e591-118">AttributeTargets Member</span></span>  
 <span data-ttu-id="9e591-119">Nell'esempio precedente è specificato **AttributeTargets** , a indicare che questo attributo può essere applicato a tutti gli elementi di programma.</span><span class="sxs-lookup"><span data-stu-id="9e591-119">In the previous example, **AttributeTargets.All** is specified, indicating that this attribute can be applied to all program elements.</span></span> <span data-ttu-id="9e591-120">In alternativa, è possibile specificare **AttributeTargets.Class**, a indicare che l'attributo può essere applicato solo a una classe, oppure **AttributeTargets.Method**, a indicare che l'attributo può essere applicato solo a un metodo.</span><span class="sxs-lookup"><span data-stu-id="9e591-120">Alternatively, you can specify **AttributeTargets.Class**, indicating that your attribute can be applied only to a class, or **AttributeTargets.Method**, indicating that your attribute can be applied only to a method.</span></span> <span data-ttu-id="9e591-121">Questa procedura può essere usata per contrassegnare tutti gli elementi di programma per la descrizione mediante un attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9e591-121">All program elements can be marked for description by a custom attribute in this manner.</span></span>  
  
 <span data-ttu-id="9e591-122">È anche possibile passare istanze multiple di <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="9e591-122">You can also pass multiple instances of <xref:System.AttributeTargets>.</span></span> <span data-ttu-id="9e591-123">Il frammento di codice seguente specifica che un attributo personalizzato può essere applicato a qualsiasi classe o metodo.</span><span class="sxs-lookup"><span data-stu-id="9e591-123">The following code fragment specifies that a custom attribute can be applied to any class or method.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
<a name="cpconwritingcustomattributesanchor2"></a>   
### <a name="inherited-property"></a><span data-ttu-id="9e591-124">Proprietà Inherited</span><span class="sxs-lookup"><span data-stu-id="9e591-124">Inherited Property</span></span>  
 <span data-ttu-id="9e591-125">La proprietà <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> indica se l'attributo può essere ereditato da classi derivate dalle classi a cui è applicato l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-125">The <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property indicates whether your attribute can be inherited by classes that are derived from the classes to which your attribute is applied.</span></span> <span data-ttu-id="9e591-126">Questa proprietà accetta un flag **true** (valore predefinito) o **false** .</span><span class="sxs-lookup"><span data-stu-id="9e591-126">This property takes either a **true** (the default) or **false** flag.</span></span> <span data-ttu-id="9e591-127">Nell'esempio seguente, ad esempio, `MyAttribute` ha una proprietà <xref:System.AttributeUsageAttribute.Inherited%2A> con il valore predefinito **true**, mentre `YourAttribute` ha una proprietà <xref:System.AttributeUsageAttribute.Inherited%2A> con valore **false**.</span><span class="sxs-lookup"><span data-stu-id="9e591-127">For example, in the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.Inherited%2A> value of **true**, while `YourAttribute` has an <xref:System.AttributeUsageAttribute.Inherited%2A> value of **false**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 <span data-ttu-id="9e591-128">I due attributi vengono quindi applicati a un metodo nella classe base `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="9e591-128">The two attributes are then applied to a method in the base class `MyClass`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 <span data-ttu-id="9e591-129">Infine, la classe `YourClass` viene ereditata dalla classe base `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="9e591-129">Finally, the class `YourClass` is inherited from the base class `MyClass`.</span></span> <span data-ttu-id="9e591-130">Il metodo `MyMethod` mostra `MyAttribute`, ma non `YourAttribute`.</span><span class="sxs-lookup"><span data-stu-id="9e591-130">The method `MyMethod` shows `MyAttribute`, but not `YourAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
<a name="cpconwritingcustomattributesanchor3"></a>   
### <a name="allowmultiple-property"></a><span data-ttu-id="9e591-131">Proprietà AllowMultiple</span><span class="sxs-lookup"><span data-stu-id="9e591-131">AllowMultiple Property</span></span>  
 <span data-ttu-id="9e591-132">La proprietà <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> indica se in un elemento possono esistere istanze multiple dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-132">The <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> property indicates whether multiple instances of your attribute can exist on an element.</span></span> <span data-ttu-id="9e591-133">Se è impostata su **true**, sono consentite istanze multiple. Se invece è impostata su **false** (valore predefinito), è consentita solo un'istanza.</span><span class="sxs-lookup"><span data-stu-id="9e591-133">If set to **true**, multiple instances are allowed; if set to **false** (the default), only one instance is allowed.</span></span>  
  
 <span data-ttu-id="9e591-134">Nell'esempio seguente `MyAttribute` ha una proprietà <xref:System.AttributeUsageAttribute.AllowMultiple%2A> con il valore predefinito **false**, mentre il valore di `YourAttribute` è **true**.</span><span class="sxs-lookup"><span data-stu-id="9e591-134">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.AllowMultiple%2A> value of **false**, while `YourAttribute` has a value of **true**.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 <span data-ttu-id="9e591-135">Quando vengono applicate istanze multiple di questi attributi, `MyAttribute` genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="9e591-135">When multiple instances of these attributes are applied, `MyAttribute` produces a compiler error.</span></span> <span data-ttu-id="9e591-136">L'esempio di codice seguente mostra l'uso valido di `YourAttribute` e l'uso non valido di `MyAttribute`.</span><span class="sxs-lookup"><span data-stu-id="9e591-136">The following code example shows the valid use of `YourAttribute` and the invalid use of `MyAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <span data-ttu-id="9e591-137">Se le proprietà <xref:System.AttributeUsageAttribute.AllowMultiple%2A> e <xref:System.AttributeUsageAttribute.Inherited%2A> sono entrambe impostate su **true**, una classe ereditata da un'altra classe può ereditare un attributo e determinare l'applicazione di un'altra istanza dello stesso attributo nella stessa classe figlio.</span><span class="sxs-lookup"><span data-stu-id="9e591-137">If both the <xref:System.AttributeUsageAttribute.AllowMultiple%2A> property and the <xref:System.AttributeUsageAttribute.Inherited%2A> property are set to **true**, a class that is inherited from another class can inherit an attribute and have another instance of the same attribute applied in the same child class.</span></span> <span data-ttu-id="9e591-138">Se la proprietà <xref:System.AttributeUsageAttribute.AllowMultiple%2A> è impostata su **false**, i valori degli attributi nella classe padre verranno sovrascritti dalle nuove istanze dello stesso attributo nella classe figlio.</span><span class="sxs-lookup"><span data-stu-id="9e591-138">If <xref:System.AttributeUsageAttribute.AllowMultiple%2A> is set to **false**, the values of any attributes in the parent class will be overwritten by new instances of the same attribute in the child class.</span></span>  
  
<a name="cpcondeclaringattributeclass"></a>   
## <a name="declaring-the-attribute-class"></a><span data-ttu-id="9e591-139">Dichiarazione della classe di attributi</span><span class="sxs-lookup"><span data-stu-id="9e591-139">Declaring the Attribute Class</span></span>  
 <span data-ttu-id="9e591-140">Dopo avere applicato <xref:System.AttributeUsageAttribute>, è possibile iniziare a definire le specifiche dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-140">After you apply the <xref:System.AttributeUsageAttribute>, you can begin to define the specifics of your attribute.</span></span> <span data-ttu-id="9e591-141">La dichiarazione di una classe di attributi è simile alla dichiarazione di una classe tradizionale, come dimostrato dal codice seguente.</span><span class="sxs-lookup"><span data-stu-id="9e591-141">The declaration of an attribute class looks similar to the declaration of a traditional class, as demonstrated by the following code.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 <span data-ttu-id="9e591-142">Questa definizione di attributo dimostra quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9e591-142">This attribute definition demonstrates the following points:</span></span>  
  
-   <span data-ttu-id="9e591-143">Le classi di attributi devono essere dichiarate come classi pubbliche.</span><span class="sxs-lookup"><span data-stu-id="9e591-143">Attribute classes must be declared as public classes.</span></span>  
  
-   <span data-ttu-id="9e591-144">Per convenzione, il nome della classe di attributi termina con la parola **Attribute**.</span><span class="sxs-lookup"><span data-stu-id="9e591-144">By convention, the name of the attribute class ends with the word **Attribute**.</span></span> <span data-ttu-id="9e591-145">Sebbene non sia obbligatorio, questa convenzione è consigliabile per migliorare la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="9e591-145">While not required, this convention is recommended for readability.</span></span> <span data-ttu-id="9e591-146">Quando l'attributo è applicato, l'inclusione della parola Attribute è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e591-146">When the attribute is applied, the inclusion of the word Attribute is optional.</span></span>  
  
-   <span data-ttu-id="9e591-147">Tutte le classi di attributi devono ereditare direttamente o indirettamente da **System.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="9e591-147">All attribute classes must inherit directly or indirectly from **System.Attribute**.</span></span>  
  
-   <span data-ttu-id="9e591-148">In Microsoft Visual Basic tutte le classi di attributi personalizzati devono avere l'attributo **AttributeUsageAttribute** .</span><span class="sxs-lookup"><span data-stu-id="9e591-148">In Microsoft Visual Basic, all custom attribute classes must have the **AttributeUsageAttribute** attribute.</span></span>  
  
<a name="cpcondeclaringconstructors"></a>   
## <a name="declaring-constructors"></a><span data-ttu-id="9e591-149">Dichiarazione dei costruttori</span><span class="sxs-lookup"><span data-stu-id="9e591-149">Declaring Constructors</span></span>  
 <span data-ttu-id="9e591-150">Gli attributi, così come le classi tradizionali, vengono inizializzati con costruttori.</span><span class="sxs-lookup"><span data-stu-id="9e591-150">Attributes are initialized with constructors in the same way as traditional classes.</span></span> <span data-ttu-id="9e591-151">Il frammento di codice seguente illustra un tipico costruttore di attributi.</span><span class="sxs-lookup"><span data-stu-id="9e591-151">The following code fragment illustrates a typical attribute constructor.</span></span> <span data-ttu-id="9e591-152">Questo costruttore pubblico accetta un parametro e ne imposta il valore uguale a una variabile membro.</span><span class="sxs-lookup"><span data-stu-id="9e591-152">This public constructor takes a parameter and sets its value equal to a member variable.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 <span data-ttu-id="9e591-153">È possibile eseguire l'overload del costruttore per supportare diverse combinazioni di valori.</span><span class="sxs-lookup"><span data-stu-id="9e591-153">You can overload the constructor to accommodate different combinations of values.</span></span> <span data-ttu-id="9e591-154">Se si definisce anche una [proprietà](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) per la classe di attributi personalizzati, è possibile usare una combinazione di parametri denominati e posizionali quando si inizializza l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-154">If you also define a [property](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52) for your custom attribute class, you can use a combination of named and positional parameters when initializing the attribute.</span></span> <span data-ttu-id="9e591-155">In genere, tutti i parametri obbligatori vengono definiti come posizionali e tutti i parametri facoltativi come denominati</span><span class="sxs-lookup"><span data-stu-id="9e591-155">Typically, you define all required parameters as positional and all optional parameters as named.</span></span> <span data-ttu-id="9e591-156">In questo caso, l'attributo non può essere inizializzato senza il parametro obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e591-156">In this case, the attribute cannot be initialized without the required parameter.</span></span> <span data-ttu-id="9e591-157">Tutti gli altri parametri sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="9e591-157">All other parameters are optional.</span></span> <span data-ttu-id="9e591-158">Si noti che, in Visual Basic, i costruttori di una classe Attribute non devono usare un argomento ParamArray.</span><span class="sxs-lookup"><span data-stu-id="9e591-158">Note that in Visual Basic, constructors for an attribute class should not use a ParamArray argument.</span></span>  
  
 <span data-ttu-id="9e591-159">L'esempio di codice seguente illustra come applicare un attributo che usa il costruttore precedente mediante i parametri obbligatori e facoltativi.</span><span class="sxs-lookup"><span data-stu-id="9e591-159">The following code example shows how an attribute that uses the previous constructor can be applied using optional and required parameters.</span></span> <span data-ttu-id="9e591-160">Presuppone che l'attributo abbia un valore booleano obbligatorio e una proprietà stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e591-160">It assumes that the attribute has one required Boolean value and one optional string property.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
<a name="cpcondeclaringproperties"></a>   
## <a name="declaring-properties"></a><span data-ttu-id="9e591-161">Dichiarazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="9e591-161">Declaring Properties</span></span>  
 <span data-ttu-id="9e591-162">Se si vuole definire un parametro denominato o fornire un modo semplice per restituire i valori archiviati dall'attributo, dichiarare una [proprietà](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span><span class="sxs-lookup"><span data-stu-id="9e591-162">If you want to define a named parameter or provide an easy way to return the values stored by your attribute, declare a [property](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span></span> <span data-ttu-id="9e591-163">Le proprietà dell'attributo devono essere dichiarate come entità pubbliche con una descrizione del tipo di dati che verrà restituito.</span><span class="sxs-lookup"><span data-stu-id="9e591-163">Attribute properties should be declared as public entities with a description of the data type that will be returned.</span></span> <span data-ttu-id="9e591-164">Definire la variabile che conterrà il valore della proprietà e associarla ai metodi **get** e **set** .</span><span class="sxs-lookup"><span data-stu-id="9e591-164">Define the variable that will hold the value of your property and associate it with the **get** and **set** methods.</span></span> <span data-ttu-id="9e591-165">L'esempio di codice seguente illustra come implementare una semplice proprietà nell'attributo.</span><span class="sxs-lookup"><span data-stu-id="9e591-165">The following code example demonstrates how to implement a simple property in your attribute.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
<a name="cpconcustomattributeexample"></a>   
## <a name="custom-attribute-example"></a><span data-ttu-id="9e591-166">esempio di attributo personalizzato</span><span class="sxs-lookup"><span data-stu-id="9e591-166">Custom Attribute Example</span></span>  
 <span data-ttu-id="9e591-167">Questa sezione include le informazioni precedenti e illustra come progettare un semplice attributo che documenta le informazioni sull'autore di una sezione di codice.</span><span class="sxs-lookup"><span data-stu-id="9e591-167">This section incorporates the previous information and shows how to design a simple attribute that documents information about the author of a section of code.</span></span> <span data-ttu-id="9e591-168">L'attributo in questo esempio archivia il nome e il livello del programmatore e specifica se il codice è stato rivisto.</span><span class="sxs-lookup"><span data-stu-id="9e591-168">The attribute in this example stores the name and level of the programmer, and whether the code has been reviewed.</span></span> <span data-ttu-id="9e591-169">Usa tre variabili private per archiviare i valori effettivi da salvare.</span><span class="sxs-lookup"><span data-stu-id="9e591-169">It uses three private variables to store the actual values to save.</span></span> <span data-ttu-id="9e591-170">Ogni variabile è rappresentata da una proprietà pubblica che ottiene e imposta i valori.</span><span class="sxs-lookup"><span data-stu-id="9e591-170">Each variable is represented by a public property that gets and sets the values.</span></span> <span data-ttu-id="9e591-171">Infine, il costruttore è definito con due parametri obbligatori.</span><span class="sxs-lookup"><span data-stu-id="9e591-171">Finally, the constructor is defined with two required parameters.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 <span data-ttu-id="9e591-172">Questo attributo può essere applicato usando il nome completo `DeveloperAttribute`oppure il nome abbreviato `Developer`in uno dei modi seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e591-172">You can apply this attribute using the full name, `DeveloperAttribute`, or using the abbreviated name, `Developer`, in one of the following ways.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 <span data-ttu-id="9e591-173">Il primo esempio mostra l'attributo applicato solo con i parametri denominati obbligatori, mentre il secondo esempio mostra l'attributo applicato con i parametri sia obbligatori che facoltativi.</span><span class="sxs-lookup"><span data-stu-id="9e591-173">The first example shows the attribute applied with only the required named parameters, while the second example shows the attribute applied with both the required and optional parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e591-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e591-174">See Also</span></span>  
 <xref:System.Attribute?displayProperty=nameWithType>  
 <xref:System.AttributeUsageAttribute>  
 [<span data-ttu-id="9e591-175">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e591-175">Attributes</span></span>](../../../docs/standard/attributes/index.md)
