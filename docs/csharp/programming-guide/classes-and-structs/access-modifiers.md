---
title: Modificatori di accesso (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
caps.latest.revision: 32
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
ms.openlocfilehash: 38b259b4d85d54467cd15cd49e5987f6198e8d99
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-programming-guide"></a><span data-ttu-id="efbb4-102">Modificatori di accesso (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="efbb4-102">Access Modifiers (C# Programming Guide)</span></span>
<span data-ttu-id="efbb4-103">Tutti i tipi e i membri dei tipi hanno un livello di accessibilità, che controlla se possono essere usati da altro codice nell'assembly o in assembly di terze parti.</span><span class="sxs-lookup"><span data-stu-id="efbb4-103">All types and type members have an accessibility level, which controls whether they can be used from other code in your assembly or other assemblies.</span></span> <span data-ttu-id="efbb4-104">È possibile usare i modificatori di accesso seguenti per specificare l'accessibilità di un tipo o di un membro quando viene dichiarato:</span><span class="sxs-lookup"><span data-stu-id="efbb4-104">You can use the following access modifiers to specify the accessibility of a type or member when you declare it:</span></span>  
  
 [<span data-ttu-id="efbb4-105">public</span><span class="sxs-lookup"><span data-stu-id="efbb4-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 <span data-ttu-id="efbb4-106">Il tipo o il membro è accessibile da altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="efbb4-106">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>  
  
 [<span data-ttu-id="efbb4-107">private</span><span class="sxs-lookup"><span data-stu-id="efbb4-107">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 <span data-ttu-id="efbb4-108">Il tipo o il membro è accessibile solo dal codice nella stessa classe o struct.</span><span class="sxs-lookup"><span data-stu-id="efbb4-108">The type or member can be accessed only by code in the same class or struct.</span></span>  
  
 [<span data-ttu-id="efbb4-109">protected</span><span class="sxs-lookup"><span data-stu-id="efbb4-109">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 <span data-ttu-id="efbb4-110">Il tipo o membro è accessibile solo dal codice nella stessa classe o struct o in una classe derivata da tale classe.</span><span class="sxs-lookup"><span data-stu-id="efbb4-110">The type or member can be accessed only by code in the same class or struct, or in a class that is derived from that class.</span></span>  
  
 [<span data-ttu-id="efbb4-111">internal</span><span class="sxs-lookup"><span data-stu-id="efbb4-111">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 <span data-ttu-id="efbb4-112">Il tipo o il membro è accessibile dal codice nello stesso assembly ma non da un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="efbb4-112">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>  
  
 `protected internal`  
 <span data-ttu-id="efbb4-113">Il tipo o il membro è accessibile da qualsiasi codice dell'assembly in cui viene dichiarato o dall'interno di una classe derivata in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="efbb4-113">The type or member can be accessed by any code in the assembly in which it is declared, or from within a derived class in another assembly.</span></span> <span data-ttu-id="efbb4-114">L'accesso da un altro assembly deve essere eseguito all'interno di una dichiarazione di classe che deriva dalla classe in cui viene dichiarato l'elemento interno protetto, e tramite un'istanza del tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="efbb4-114">Access from another assembly must take place within a class declaration that derives from the class in which the protected internal element is declared, and it must take place through an instance of the derived class type.</span></span>  
  
 <span data-ttu-id="efbb4-115">L'esempio seguente illustra come specificare i modificatori di accesso in un tipo e in un membro:</span><span class="sxs-lookup"><span data-stu-id="efbb4-115">The following examples demonstrate how to specify access modifiers on a type and member:</span></span>  
  
 <span data-ttu-id="efbb4-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="efbb4-116">[!code-cs[csProgGuideObjects#72](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_1.cs)]</span></span>  
  
 <span data-ttu-id="efbb4-117">Non tutti i modificatori di accesso possono essere usati da tutti i tipi o membri in tutti i contesti e in alcuni casi l'accessibilità di un membro del tipo è vincolato all'accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="efbb4-117">Not all access modifiers can be used by all types or members in all contexts, and in some cases the accessibility of a type member is constrained by the accessibility of its containing type.</span></span> <span data-ttu-id="efbb4-118">Le sezioni seguenti offrono altre informazioni dettagliate sull'accessibilità.</span><span class="sxs-lookup"><span data-stu-id="efbb4-118">The following sections provide more details about accessibility.</span></span>  
  
## <a name="class-and-struct-accessibility"></a><span data-ttu-id="efbb4-119">Accessibilità di classi e struct</span><span class="sxs-lookup"><span data-stu-id="efbb4-119">Class and Struct Accessibility</span></span>  
 <span data-ttu-id="efbb4-120">Le classi e gli struct dichiarati direttamente all'interno di uno spazio dei nomi (in altre parole, che non sono annidati all'interno di altre classi o struct) possono essere public o internal.</span><span class="sxs-lookup"><span data-stu-id="efbb4-120">Classes and structs that are declared directly within a namespace (in other words, that are not nested within other classes or structs) can be either public or internal.</span></span> <span data-ttu-id="efbb4-121">Internal è l'opzione predefinita se non viene specificato nessun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="efbb4-121">Internal is the default if no access modifier is specified.</span></span>  
  
 <span data-ttu-id="efbb4-122">I membri struct, incluse le classi e gli struct annidati, possono essere dichiarati come public, internal o private.</span><span class="sxs-lookup"><span data-stu-id="efbb4-122">Struct members, including nested classes and structs, can be declared as public, internal, or private.</span></span> <span data-ttu-id="efbb4-123">I membri struct, incluse le classi e gli struct annidati, possono essere public, protected internal, protected, internal o private.</span><span class="sxs-lookup"><span data-stu-id="efbb4-123">Class members, including nested classes and structs, can be public, protected internal, protected, internal, or private.</span></span> <span data-ttu-id="efbb4-124">Il livello di accesso per i membri di classe e per i membri struct, incluse le classi e gli struct annidati, è private per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="efbb4-124">The access level for class members and struct members, including nested classes and structs, is private by default.</span></span> <span data-ttu-id="efbb4-125">I tipi annidati private non sono accessibili all'esterno del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="efbb4-125">Private nested types are not accessible from outside the containing type.</span></span>  
  
 <span data-ttu-id="efbb4-126">Le classi derivate non possono avere un'accessibilità maggiore di quella dei tipi di base.</span><span class="sxs-lookup"><span data-stu-id="efbb4-126">Derived classes cannot have greater accessibility than their base types.</span></span> <span data-ttu-id="efbb4-127">In altre parole, non è possibile avere una classe `B` public che deriva da una classe `A` internal.</span><span class="sxs-lookup"><span data-stu-id="efbb4-127">In other words, you cannot have a public class `B` that derives from an internal class `A`.</span></span> <span data-ttu-id="efbb4-128">Se questo fosse consentito, avrebbe l'effetto di rendere `A` pubblic, perché tutti i membri protected e internal di `A` sarebbero accessibili dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="efbb4-128">If this were allowed, it would have the effect of making `A` public, because all protected or internal members of `A` are accessible from the derived class.</span></span>  
  
 <span data-ttu-id="efbb4-129">È possibile abilitare altri assembly specifici per accedere ai tipi internal usando InternalsVisibleToAttribute.</span><span class="sxs-lookup"><span data-stu-id="efbb4-129">You can enable specific other assemblies to access your internal types by using the InternalsVisibleToAttribute.</span></span> <span data-ttu-id="efbb4-130">Per altre informazioni, vedere [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055) (Assembly friend).</span><span class="sxs-lookup"><span data-stu-id="efbb4-130">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="class-and-struct-member-accessibility"></a><span data-ttu-id="efbb4-131">Accessibilità dei membri struct e di classe</span><span class="sxs-lookup"><span data-stu-id="efbb4-131">Class and Struct Member Accessibility</span></span>  
 <span data-ttu-id="efbb4-132">I membri di classe (inclusi le classi e gli struct annidati) possono essere dichiarati con uno qualsiasi dei cinque tipi di accesso.</span><span class="sxs-lookup"><span data-stu-id="efbb4-132">Class members (including nested classes and structs) can be declared with any of the five types of access.</span></span> <span data-ttu-id="efbb4-133">I membri struct non possono essere dichiarati protected perché struct non supporta l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="efbb4-133">Struct members cannot be declared as protected because structs do not support inheritance.</span></span>  
  
 <span data-ttu-id="efbb4-134">In genere l'accessibilità di un membro non è maggiore dell'accessibilità del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="efbb4-134">Normally, the accessibility of a member is not greater than the accessibility of the type that contains it.</span></span> <span data-ttu-id="efbb4-135">Un membro public di una classe internal potrebbe tuttavia essere accessibile dall'esterno dell'assembly se il membro implementa metodi di interfaccia o esegue l'override di metodi virtuali definiti in una classe di base public.</span><span class="sxs-lookup"><span data-stu-id="efbb4-135">However, a public member of an internal class might be accessible from outside the assembly if the member implements interface methods or overrides virtual methods that are defined in a public base class.</span></span>  
  
 <span data-ttu-id="efbb4-136">Il tipo di qualsiasi membro che è un campo, proprietà o evento deve essere accessibile almeno quanto il membro stesso.</span><span class="sxs-lookup"><span data-stu-id="efbb4-136">The type of any member that is a field, property, or event must be at least as accessible as the member itself.</span></span> <span data-ttu-id="efbb4-137">Analogamente, il tipo restituito e i tipi di parametri di qualsiasi membro, che è un metodo, indicizzatore o delegato, devono essere accessibili almeno quanto il membro stesso.</span><span class="sxs-lookup"><span data-stu-id="efbb4-137">Similarly, the return type and the parameter types of any member that is a method, indexer, or delegate must be at least as accessible as the member itself.</span></span> <span data-ttu-id="efbb4-138">Ad esempio, non è possibile avere un metodo `M` public che restituisce una classe `C` a meno che `C` non sia anche public.</span><span class="sxs-lookup"><span data-stu-id="efbb4-138">For example, you cannot have a public method `M` that returns a class `C` unless `C` is also public.</span></span> <span data-ttu-id="efbb4-139">Analogamente, non è possibile avere una proprietà protected di tipo `A` se `A` è dichiarato come private.</span><span class="sxs-lookup"><span data-stu-id="efbb4-139">Likewise, you cannot have a protected property of type `A` if `A` is declared as private.</span></span>  
  
 <span data-ttu-id="efbb4-140">Gli operatori definiti dall'utente devono sempre essere dichiarati come public.</span><span class="sxs-lookup"><span data-stu-id="efbb4-140">User-defined operators must always be declared as public.</span></span> <span data-ttu-id="efbb4-141">Per altre informazioni, vedere [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="efbb4-141">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
 <span data-ttu-id="efbb4-142">I finalizzatori non possono avere modificatori di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="efbb4-142">Finalizers cannot have accessibility modifiers.</span></span>  
  
 <span data-ttu-id="efbb4-143">Per impostare il livello di accesso per un membro struct o di classe, aggiungere la parola chiave appropriata alla dichiarazione del membro, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="efbb4-143">To set the access level for a class or struct member, add the appropriate keyword to the member declaration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="efbb4-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="efbb4-144">[!code-cs[csProgGuideObjects#73](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/access-modifiers_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efbb4-145">Il livello di accessibilità protected internal significa protected O internal, ma non protected E internal.</span><span class="sxs-lookup"><span data-stu-id="efbb4-145">The protected internal accessibility level means protected OR internal, not protected AND internal.</span></span> <span data-ttu-id="efbb4-146">In altre parole, un membro protected internal è accessibile da qualsiasi classe dello stesso assembly, incluse le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="efbb4-146">In other words, a protected internal member can be accessed from any class in the same assembly, including derived classes.</span></span> <span data-ttu-id="efbb4-147">Per limitare l'accessibilità solo alle classi derivate dello stesso assembly, dichiarare la classe stessa come internal e dichiarare i relativi membri come protected.</span><span class="sxs-lookup"><span data-stu-id="efbb4-147">To limit accessibility to only derived classes in the same assembly, declare the class itself internal, and declare its members as protected.</span></span>  
  
## <a name="other-types"></a><span data-ttu-id="efbb4-148">Altri tipi</span><span class="sxs-lookup"><span data-stu-id="efbb4-148">Other Types</span></span>  
 <span data-ttu-id="efbb4-149">Le interfacce dichiarate direttamente all'interno di uno spazio dei nomi possono essere dichiarate come public o internal e, analogamente a classi e struct, le interfacce vengono impostate a accesso internal.</span><span class="sxs-lookup"><span data-stu-id="efbb4-149">Interfaces declared directly within a namespace can be declared as public or internal and, just like classes and structs, interfaces default to internal access.</span></span> <span data-ttu-id="efbb4-150">I membri di interfaccia sono sempre public poiché lo scopo di un'interfaccia è abilitare altri tipi ad accedere a una classe o struct.</span><span class="sxs-lookup"><span data-stu-id="efbb4-150">Interface members are always public because the purpose of an interface is to enable other types to access a class or struct.</span></span> <span data-ttu-id="efbb4-151">Nessun modificatore di accesso può essere applicato ai membri di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="efbb4-151">No access modifiers can be applied to interface members.</span></span>  
  
 <span data-ttu-id="efbb4-152">I membri di enumerazione sono sempre public e non può essere applicato nessun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="efbb4-152">Enumeration members are always public, and no access modifiers can be applied.</span></span>  
  
 <span data-ttu-id="efbb4-153">I delegati si comportano come classi e struct.</span><span class="sxs-lookup"><span data-stu-id="efbb4-153">Delegates behave like classes and structs.</span></span> <span data-ttu-id="efbb4-154">Per impostazione predefinita, hanno accesso internal quando dichiarati direttamente all'interno di uno spazio dei nomi e accesso private se annidati.</span><span class="sxs-lookup"><span data-stu-id="efbb4-154">By default, they have internal access when declared directly within a namespace, and private access when nested.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="efbb4-155">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="efbb4-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="efbb4-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efbb4-156">See Also</span></span>  
 <span data-ttu-id="efbb4-157">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-157">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="efbb4-158">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-158">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="efbb4-159">[Interfacce](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-159">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="efbb4-160">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-160">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="efbb4-161">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-161">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="efbb4-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-162">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="efbb4-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-163">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 <span data-ttu-id="efbb4-164">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-164">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="efbb4-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="efbb4-165">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="efbb4-166">interface</span><span class="sxs-lookup"><span data-stu-id="efbb4-166">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)

