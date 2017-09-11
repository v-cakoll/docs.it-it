---
title: event (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="17e6e-102">event (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="17e6e-102">event (C# Reference)</span></span>
<span data-ttu-id="17e6e-103">La parola chiave `event` viene usata per dichiarare un evento in una classe autore.</span><span class="sxs-lookup"><span data-stu-id="17e6e-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17e6e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="17e6e-104">Example</span></span>  
 <span data-ttu-id="17e6e-105">L'esempio seguente illustra come dichiarare e generare un evento che usa <xref:System.EventHandler> come tipo di delegato sottostante.</span><span class="sxs-lookup"><span data-stu-id="17e6e-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="17e6e-106">Per l'esempio di codice completo che illustra anche come usare il tipo di delegato generico <xref:System.EventHandler%601> e come sottoscrivere un evento e creare un metodo per il gestore dell'evento, vedere [Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="17e6e-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="17e6e-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="17e6e-108">Gli eventi sono un tipo di delegati multicast speciali che possono essere chiamati solo dall'interno della classe o dello struct in cui sono dichiarati (la classe autore).</span><span class="sxs-lookup"><span data-stu-id="17e6e-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="17e6e-109">Se altre classi o altri struct sottoscrivono l'evento, i metodi di gestione eventi corrispondenti verranno chiamati quando la classe publisher genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="17e6e-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="17e6e-110">Per altre informazioni e altri esempi di codice, vedere [Eventi](../../../csharp/programming-guide/events/index.md) e [Delegati](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="17e6e-111">Gli eventi possono essere contrassegnati come [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="17e6e-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="17e6e-112">Questi modificatori di accesso definiscono in che modo gli utenti della classe possono accedere all'evento.</span><span class="sxs-lookup"><span data-stu-id="17e6e-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="17e6e-113">Per altre informazioni, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="17e6e-114">Parole chiave ed eventi</span><span class="sxs-lookup"><span data-stu-id="17e6e-114">Keywords and Events</span></span>  
 <span data-ttu-id="17e6e-115">Agli eventi si applicano le parole chiave seguenti.</span><span class="sxs-lookup"><span data-stu-id="17e6e-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="17e6e-116">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="17e6e-116">Keyword</span></span>|<span data-ttu-id="17e6e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17e6e-117">Description</span></span>|<span data-ttu-id="17e6e-118">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="17e6e-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="17e6e-119">static</span><span class="sxs-lookup"><span data-stu-id="17e6e-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="17e6e-120">Rende l'evento disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="17e6e-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="17e6e-121">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="17e6e-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="17e6e-122">virtual</span><span class="sxs-lookup"><span data-stu-id="17e6e-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="17e6e-123">Consente alle classi derivate di eseguire l'override del comportamento dell'evento tramite la parola chiave [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="17e6e-124">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="17e6e-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="17e6e-125">sealed</span><span class="sxs-lookup"><span data-stu-id="17e6e-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="17e6e-126">Specifica che per le classi derivate l'evento non è più virtuale.</span><span class="sxs-lookup"><span data-stu-id="17e6e-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="17e6e-127">abstract</span><span class="sxs-lookup"><span data-stu-id="17e6e-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="17e6e-128">Il compilatore non genererà i blocchi di funzioni di accesso degli eventi `add` e `remove` e pertanto le classi derivate dovranno fornire la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="17e6e-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="17e6e-129">Un evento può essere dichiarato statico mediante la parola chiave [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="17e6e-130">Ciò rende l'evento disponibile per i chiamanti in qualsiasi momento, anche se non esiste alcuna istanza della classe.</span><span class="sxs-lookup"><span data-stu-id="17e6e-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="17e6e-131">Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="17e6e-132">Un evento può essere contrassegnato come virtuale mediante la parola chiave [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="17e6e-133">Ciò consente alle classi derivate di eseguire l'override del comportamento dell'evento tramite la parola chiave [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="17e6e-134">Per altre informazioni, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="17e6e-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="17e6e-135">Un evento che esegue l'override di un evento virtuale può anche essere contrassegnato come [sealed](../../../csharp/language-reference/keywords/sealed.md), in modo che non risulti più virtuale per le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="17e6e-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="17e6e-136">Infine, un evento può essere dichiarato [abstract](../../../csharp/language-reference/keywords/abstract.md), in modo che il compilatore non generi blocchi di funzioni di accesso agli eventi `add` e `remove`.</span><span class="sxs-lookup"><span data-stu-id="17e6e-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="17e6e-137">Le classi derivate devono pertanto fornire la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="17e6e-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="17e6e-138">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="17e6e-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="17e6e-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17e6e-139">See Also</span></span>  
 <span data-ttu-id="17e6e-140">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="17e6e-141">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="17e6e-142">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="17e6e-143">[add](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="17e6e-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="17e6e-145">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="17e6e-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="17e6e-146">Procedura: Combinare delegati (delegati multicast)</span><span class="sxs-lookup"><span data-stu-id="17e6e-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

