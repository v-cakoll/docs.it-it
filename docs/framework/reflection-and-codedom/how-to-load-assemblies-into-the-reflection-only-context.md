---
title: 'Procedura: caricare assembly nel contesto Reflection-Only'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: cac6b3b3adf070ad6070e5c5941653f20dedd907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130109"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="21fdc-102">Procedura: caricare assembly nel contesto Reflection-Only</span><span class="sxs-lookup"><span data-stu-id="21fdc-102">How to: Load Assemblies into the Reflection-Only Context</span></span>

<span data-ttu-id="21fdc-103">Il contesto di caricamento di sola reflection consente di esaminare gli assembly compilati per altre piattaforme o altre versioni di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21fdc-103">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="21fdc-104">Il codice caricato in questo contesto può essere solo esaminato e non eseguito.</span><span class="sxs-lookup"><span data-stu-id="21fdc-104">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="21fdc-105">Di conseguenza, poiché i costruttori non possono essere eseguiti, non è possibile creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="21fdc-105">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="21fdc-106">Non essendo possibile eseguire il codice, le dipendenze non vengono caricate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="21fdc-106">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="21fdc-107">Per esaminarle, è necessario caricarle manualmente.</span><span class="sxs-lookup"><span data-stu-id="21fdc-107">If you need to examine them, you must load them yourself.</span></span>

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="21fdc-108">Per caricare un assembly nel contesto di caricamento di sola reflection</span><span class="sxs-lookup"><span data-stu-id="21fdc-108">To load an assembly into the reflection-only load context</span></span>

1. <span data-ttu-id="21fdc-109">Usare l'overload del metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> per caricare l'assembly in base al nome di visualizzazione oppure il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> per caricare l'assembly in base al percorso.</span><span class="sxs-lookup"><span data-stu-id="21fdc-109">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="21fdc-110">Se l'assembly è un'immagine binaria, usare l'overload del metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="21fdc-110">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>

    > [!NOTE]
    > <span data-ttu-id="21fdc-111">Non è possibile usare il contesto di sola reflection per caricare una versione di mscorlib.dll da una versione di .NET Framework diversa da quella installata nel contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21fdc-111">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>

2. <span data-ttu-id="21fdc-112">Se l'assembly contiene dipendenze, queste ultime non verranno caricate dal metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>.</span><span class="sxs-lookup"><span data-stu-id="21fdc-112">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="21fdc-113">Per esaminarle, è necessario caricarle manualmente.</span><span class="sxs-lookup"><span data-stu-id="21fdc-113">If you need to examine them, you must load them yourself.</span></span>

3. <span data-ttu-id="21fdc-114">Determinare se un assembly viene caricato nel contesto di sola reflection usando la proprietà <xref:System.Reflection.Assembly.ReflectionOnly%2A> dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="21fdc-114">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>

4. <span data-ttu-id="21fdc-115">Se all'assembly o ai tipi in esso contenuti sono applicati attributi, esaminare gli attributi usando la classe <xref:System.Reflection.CustomAttributeData> per assicurarsi che non venga effettuato alcun tentativo di eseguire il codice nel contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="21fdc-115">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="21fdc-116">Usare l'overload appropriato del metodo <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> per ottenere gli oggetti <xref:System.Reflection.CustomAttributeData> che rappresentano gli attributi applicati a un assembly, membro, modulo o parametro.</span><span class="sxs-lookup"><span data-stu-id="21fdc-116">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>

    > [!NOTE]
    > <span data-ttu-id="21fdc-117">Gli attributi applicati all'assembly o al relativo contenuto possono essere definiti nell'assembly o in un altro assembly caricato nel contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="21fdc-117">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="21fdc-118">Non è possibile stabilire in anticipo dove sono definiti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="21fdc-118">There is no way to tell in advance where the attributes are defined.</span></span>

## <a name="example"></a><span data-ttu-id="21fdc-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="21fdc-119">Example</span></span>

<span data-ttu-id="21fdc-120">L'esempio di codice seguente illustra come esaminare gli attributi applicati a un assembly caricato nel contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="21fdc-120">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>

<span data-ttu-id="21fdc-121">L'esempio di codice definisce un attributo personalizzato con due costruttori e una proprietà.</span><span class="sxs-lookup"><span data-stu-id="21fdc-121">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="21fdc-122">L'attributo è applicato all'assembly, a un tipo dichiarato nell'assembly, a un metodo del tipo e a un parametro del metodo.</span><span class="sxs-lookup"><span data-stu-id="21fdc-122">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="21fdc-123">Quando viene eseguito, l'assembly viene caricato nel contesto di sola reflection e vengono visualizzate informazioni sugli attributi personalizzati applicati all'assembly e ai tipi e membri che contiene.</span><span class="sxs-lookup"><span data-stu-id="21fdc-123">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>

> [!NOTE]
> <span data-ttu-id="21fdc-124">Per semplificare l'esempio di codice, l'assembly carica ed esamina se stesso.</span><span class="sxs-lookup"><span data-stu-id="21fdc-124">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="21fdc-125">In genere, non è probabile che lo stesso assembly venga caricato sia nel contesto di esecuzione che nel contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="21fdc-125">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="21fdc-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21fdc-126">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
