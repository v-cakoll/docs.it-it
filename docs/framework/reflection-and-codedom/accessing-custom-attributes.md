---
title: Accesso ad attributi personalizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6955c24c12936ef37bedea2a1dd290bac45a5a2e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894908"
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="aee17-102">Accesso ad attributi personalizzati</span><span class="sxs-lookup"><span data-stu-id="aee17-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="aee17-103">Dopo che gli attributi sono stati associati a elementi del programma, è possibile verificarne l'esistenza ed esaminarne i valori tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="aee17-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="aee17-104">In .NET Framework versioni 1.0 e 1.1 gli attributi personalizzati vengono esaminati nel contesto di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aee17-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="aee17-105">.NET Framework versione 2.0 offre un nuovo contesto di caricamento di sola reflection, che consente di esaminare il codice che non può essere caricato per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="aee17-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="aee17-106">Contesto di sola reflection</span><span class="sxs-lookup"><span data-stu-id="aee17-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="aee17-107">Il codice caricato nel contesto di sola reflection non può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="aee17-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="aee17-108">Non è pertanto possibile creare istanze di attributi personalizzati, operazione per cui è richiesta l'esecuzione dei costruttori.</span><span class="sxs-lookup"><span data-stu-id="aee17-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="aee17-109">Per caricare ed esaminare gli attributi personalizzati nel contesto di sola reflection, usare la classe <xref:System.Reflection.CustomAttributeData>.</span><span class="sxs-lookup"><span data-stu-id="aee17-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="aee17-110">È possibile ottenere istanze di questa classe usando l'overload appropriato del metodo <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> statico.</span><span class="sxs-lookup"><span data-stu-id="aee17-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aee17-111">Vedere [Procedura: Caricare assembly nel contesto Reflection-Only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="aee17-111">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="aee17-112">Contesto di esecuzione</span><span class="sxs-lookup"><span data-stu-id="aee17-112">The Execution Context</span></span>  
 <span data-ttu-id="aee17-113">I principali metodi di reflection per l'esecuzione di query sugli attributi nel contesto di esecuzione sono <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> e <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aee17-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="aee17-114">L'accessibilità di un attributo personalizzato viene controllata in riferimento all'assembly a cui l'attributo è collegato.</span><span class="sxs-lookup"><span data-stu-id="aee17-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="aee17-115">In altri termini, si verifica se un metodo di un tipo dell'assembly a cui è collegato l'attributo personalizzato può chiamare il costruttore dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aee17-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="aee17-116">I metodi come <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> consentono di controllare la visibilità e l'accessibilità dell'argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="aee17-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="aee17-117">È possibile recuperare un attributo personalizzato del tipo definito dall'utente tramite **GetCustomAttributes** solo nel codice dell'assembly che contiene tale tipo.</span><span class="sxs-lookup"><span data-stu-id="aee17-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="aee17-118">Nell'esempio in C# riportato di seguito viene rappresentato un tipico modello di progettazione di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="aee17-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="aee17-119">Viene illustrato il modello di reflection degli attributi personalizzati adottato dal runtime.</span><span class="sxs-lookup"><span data-stu-id="aee17-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```csharp
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="aee17-120">Se il runtime tenta di recuperare gli attributi personalizzati del tipo di attributo personalizzato pubblico <xref:System.ComponentModel.DescriptionAttribute> associato al metodo **GetLanguage**, esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aee17-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1. <span data-ttu-id="aee17-121">Controlla che l'argomento di tipo **DescriptionAttribute** a **Type.GetCustomAttributes**(Tipo *tipo*) sia pubblico e quindi visibile e accessibile.</span><span class="sxs-lookup"><span data-stu-id="aee17-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2. <span data-ttu-id="aee17-122">Controlla che il tipo definito dall'utente **MyDescriptionAttribute** che deriva da **DescriptionAttribute** sia visibile e accessibile all'interno dell'assembly **System.Web.DLL**, in cui è collegato al metodo **GetLanguage**().</span><span class="sxs-lookup"><span data-stu-id="aee17-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3. <span data-ttu-id="aee17-123">Controlla che il costruttore di **MyDescriptionAttribute** sia visibile e accessibile all'interno dell'assembly **System.Web.DLL**.</span><span class="sxs-lookup"><span data-stu-id="aee17-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4. <span data-ttu-id="aee17-124">Chiama il costruttore di **MyDescriptionAttribute** con i parametri dell'attributo personalizzato e restituisce il nuovo oggetto al chiamante.</span><span class="sxs-lookup"><span data-stu-id="aee17-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="aee17-125">Il modello di reflection degli attributi personalizzati può perdere istanze di tipi definiti dall'utente all'esterno dell'assembly in cui il tipo è definito.</span><span class="sxs-lookup"><span data-stu-id="aee17-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="aee17-126">Questo modello non differisce da quello in cui si inquadrano i membri della libreria di sistema del runtime, che restituiscono istanze di tipi definiti dall'utente, come <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> che restituisce una matrice di oggetti **RuntimeMethodInfo**.</span><span class="sxs-lookup"><span data-stu-id="aee17-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="aee17-127">Per impedire a un client di rilevare informazioni su un attributo personalizzato definito dall'utente, definire i membri del tipo come non pubblici.</span><span class="sxs-lookup"><span data-stu-id="aee17-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="aee17-128">Nell'esempio seguente viene illustrato il metodo principale per accedere agli attributi personalizzati tramite reflection.</span><span class="sxs-lookup"><span data-stu-id="aee17-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="aee17-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee17-129">See also</span></span>

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aee17-130">Visualizzazione delle informazioni sul tipo</span><span class="sxs-lookup"><span data-stu-id="aee17-130">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
- <span data-ttu-id="aee17-131">[Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md) (Considerazioni sulla sicurezza per reflection)</span><span class="sxs-lookup"><span data-stu-id="aee17-131">[Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)</span></span>
