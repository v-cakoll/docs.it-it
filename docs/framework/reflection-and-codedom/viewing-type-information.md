---
title: Visualizzazione delle informazioni sul tipo
description: Consente di visualizzare le informazioni sul tipo utilizzando System. Type, che è fondamentale per la reflection in .NET. Esaminare ConstructorInfo, MemberInfo, MethodInfo, FieldInfo e PropertyInfo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: cd74021e1f1a79626e171db13def98e546cd51df
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865203"
---
# <a name="viewing-type-information"></a><span data-ttu-id="b92fa-104">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="b92fa-104">Viewing Type Information</span></span>
<span data-ttu-id="b92fa-105">La classe <xref:System.Type?displayProperty=nameWithType> è fondamentale per la reflection.</span><span class="sxs-lookup"><span data-stu-id="b92fa-105">The <xref:System.Type?displayProperty=nameWithType> class is central to reflection.</span></span> <span data-ttu-id="b92fa-106">Quando la reflection lo richiede, Common Language Runtime crea l'oggetto **Type** relativo a un tipo caricato.</span><span class="sxs-lookup"><span data-stu-id="b92fa-106">The common language runtime creates the **Type** for a loaded type when reflection requests it.</span></span> <span data-ttu-id="b92fa-107">Per ottenere informazioni sul tipo, è possibile usare metodi, campi, proprietà e classi nidificate dell'oggetto **Type**.</span><span class="sxs-lookup"><span data-stu-id="b92fa-107">You can use a **Type** object's methods, fields, properties, and nested classes to find out everything about that type.</span></span>  
  
 <span data-ttu-id="b92fa-108">Usare <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> per ottenere oggetti **Type** da assembly che non sono stati caricati, passando il nome del tipo o dei tipi desiderati.</span><span class="sxs-lookup"><span data-stu-id="b92fa-108">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> to obtain **Type** objects from assemblies that have not been loaded, passing in the name of the type or types you want.</span></span> <span data-ttu-id="b92fa-109">Usare <xref:System.Type.GetType%2A?displayProperty=nameWithType> per ottenere oggetti **Type** da un assembly già caricato.</span><span class="sxs-lookup"><span data-stu-id="b92fa-109">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> to get the **Type** objects from an assembly that is already loaded.</span></span> <span data-ttu-id="b92fa-110">Usare <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> e <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> per ottenere gli oggetti **Type** dei moduli.</span><span class="sxs-lookup"><span data-stu-id="b92fa-110">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> and <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> to obtain module **Type** objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b92fa-111">Se si vuole esaminare e modificare tipi e metodi generici, vedere le altre informazioni disponibili in [Reflection e tipi generici](reflection-and-generic-types.md) e [Procedura: Esaminare e creare istanze di tipi generici tramite reflection](how-to-examine-and-instantiate-generic-types-with-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b92fa-111">If you want to examine and manipulate generic types and methods, please see the additional information provided in [Reflection and Generic Types](reflection-and-generic-types.md) and [How to: Examine and Instantiate Generic Types with Reflection](how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="b92fa-112">L'esempio seguente illustra la sintassi necessaria per ottenere il modulo e l'oggetto <xref:System.Reflection.Assembly> per un assembly.</span><span class="sxs-lookup"><span data-stu-id="b92fa-112">The following example shows the syntax necessary to get the <xref:System.Reflection.Assembly> object and module for an assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 <span data-ttu-id="b92fa-113">L'esempio seguente descrive come ottenere oggetti **Type** per un assembly caricato.</span><span class="sxs-lookup"><span data-stu-id="b92fa-113">The following example demonstrates getting **Type** objects from a loaded assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 <span data-ttu-id="b92fa-114">Dopo aver ottenuto un oggetto **Type**, è possibile ottenere informazioni sui membri del tipo in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="b92fa-114">Once you obtain a **Type**, there are many ways you can discover information about the members of that type.</span></span> <span data-ttu-id="b92fa-115">Ad esempio, per ottenere informazioni su tutti i membri del tipo è possibile chiamare il metodo <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> che ottiene una matrice di oggetti <xref:System.Reflection.MemberInfo> ognuno dei quali descrive un membro del tipo corrente.</span><span class="sxs-lookup"><span data-stu-id="b92fa-115">For example, you can find out about all the type's members by calling the <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> method, which obtains an array of <xref:System.Reflection.MemberInfo> objects describing each of the members of the current type.</span></span>  
  
 <span data-ttu-id="b92fa-116">È anche possibile usare i metodi nella classe **Type** per recuperare informazioni su uno o più costruttori, metodi, eventi, campi o proprietà di cui si specifica il nome.</span><span class="sxs-lookup"><span data-stu-id="b92fa-116">You can also use methods on the **Type** class to retrieve information about one or more constructors, methods, events, fields, or properties that you specify by name.</span></span> <span data-ttu-id="b92fa-117">Ad esempio, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> incapsula uno costruttore specifico della classe corrente.</span><span class="sxs-lookup"><span data-stu-id="b92fa-117">For example, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsulates a specific constructor of the current class.</span></span>  
  
 <span data-ttu-id="b92fa-118">Se è presente un oggetto **Type** è possibile usare la proprietà <xref:System.Type.Module%2A?displayProperty=nameWithType> per ottenere un oggetto che incapsula il modulo contenente il tipo.</span><span class="sxs-lookup"><span data-stu-id="b92fa-118">If you have a **Type**, you can use the <xref:System.Type.Module%2A?displayProperty=nameWithType> property to obtain an object that encapsulates the module containing that type.</span></span> <span data-ttu-id="b92fa-119">Usare la proprietà <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> per individuare un oggetto che incapsula l'assembly contenente il modulo.</span><span class="sxs-lookup"><span data-stu-id="b92fa-119">Use the <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> property to locate an object that encapsulates the assembly containing the module.</span></span> <span data-ttu-id="b92fa-120">Per ottenere direttamente l'assembly che incapsula il tipo, usare la proprietà <xref:System.Type.Assembly%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b92fa-120">You can obtain the assembly that encapsulates the type directly by using the <xref:System.Type.Assembly%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="systemtype-and-constructorinfo"></a><span data-ttu-id="b92fa-121">System.Type e ConstructorInfo</span><span class="sxs-lookup"><span data-stu-id="b92fa-121">System.Type and ConstructorInfo</span></span>  
 <span data-ttu-id="b92fa-122">L'esempio seguente illustra come elencare i costruttori di una classe, nel caso specifico la classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b92fa-122">The following example shows how to list the constructors for a class, in this case, the <xref:System.String> class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a><span data-ttu-id="b92fa-123">MemberInfo, MethodInfo, FieldInfo e PropertyInfo</span><span class="sxs-lookup"><span data-stu-id="b92fa-123">MemberInfo, MethodInfo, FieldInfo, and PropertyInfo</span></span>  
 <span data-ttu-id="b92fa-124">Per ottenere informazioni su metodi, proprietà, eventi e campi del tipo, usare gli oggetti <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> o <xref:System.Reflection.PropertyInfo>.</span><span class="sxs-lookup"><span data-stu-id="b92fa-124">Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo>, or <xref:System.Reflection.PropertyInfo> objects.</span></span>  
  
 <span data-ttu-id="b92fa-125">L'esempio seguente usa **MemberInfo** per elencare il numero di membri della classe **System.IO.File** e usa la proprietà <xref:System.Type.IsPublic%2A> per determinare la visibilità della classe.</span><span class="sxs-lookup"><span data-stu-id="b92fa-125">The following example uses **MemberInfo** to list the number of members in the **System.IO.File** class and uses the <xref:System.Type.IsPublic%2A> property to determine the visibility of the class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 <span data-ttu-id="b92fa-126">L'esempio seguente analizza il tipo del membro specificato.</span><span class="sxs-lookup"><span data-stu-id="b92fa-126">The following example investigates the type of the specified member.</span></span> <span data-ttu-id="b92fa-127">Viene eseguita una reflection su un membro della classe **MemberInfo** e ne viene elencato il tipo.</span><span class="sxs-lookup"><span data-stu-id="b92fa-127">It performs reflection on a member of the **MemberInfo** class, and lists its type.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 <span data-ttu-id="b92fa-128">Nell'esempio seguente vengono utilizzate tutte le classi di \*\* \* informazioni\*\* di Reflection insieme <xref:System.Reflection.BindingFlags> a per elencare tutti i membri (costruttori, campi, proprietà, eventi e metodi) della classe specificata, dividendo i membri in categorie statiche e di istanza.</span><span class="sxs-lookup"><span data-stu-id="b92fa-128">The following example uses all the Reflection **\*Info** classes along with <xref:System.Reflection.BindingFlags> to list all the members (constructors, fields, properties, events, and methods) of the specified class, dividing the members into static and instance categories.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b92fa-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b92fa-129">See also</span></span>

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [<span data-ttu-id="b92fa-130">Reflection e tipi generici</span><span class="sxs-lookup"><span data-stu-id="b92fa-130">Reflection and Generic Types</span></span>](reflection-and-generic-types.md)
