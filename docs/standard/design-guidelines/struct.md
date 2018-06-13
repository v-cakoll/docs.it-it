---
title: Progettazione di struct
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2621aa96cf89b453d5faec3357d0890ca36251d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572736"
---
# <a name="struct-design"></a><span data-ttu-id="f75b6-102">Progettazione di struct</span><span class="sxs-lookup"><span data-stu-id="f75b6-102">Struct Design</span></span>
<span data-ttu-id="f75b6-103">Il tipo di valore generici è più noto anche come una struttura, la parola chiave c#.</span><span class="sxs-lookup"><span data-stu-id="f75b6-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="f75b6-104">In questa sezione vengono fornite linee guida per la progettazione struttura generale.</span><span class="sxs-lookup"><span data-stu-id="f75b6-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="f75b6-105">**X non** fornisce un costruttore predefinito per uno struct.</span><span class="sxs-lookup"><span data-stu-id="f75b6-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="f75b6-106">Seguendo questa linea guida gli matrici di strutture possono essere creati senza dover eseguire il costruttore su ogni elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="f75b6-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="f75b6-107">Si noti che in c# non consente strutture possono disporre di costruttori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f75b6-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="f75b6-108">**X non** definire i tipi di valore modificabile.</span><span class="sxs-lookup"><span data-stu-id="f75b6-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="f75b6-109">Tipi di valore modificabile hanno vari problemi.</span><span class="sxs-lookup"><span data-stu-id="f75b6-109">Mutable value types have several problems.</span></span> <span data-ttu-id="f75b6-110">Ad esempio, quando una proprietà get restituisce un tipo di valore, il chiamante riceve una copia.</span><span class="sxs-lookup"><span data-stu-id="f75b6-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="f75b6-111">Poiché la copia viene creata in modo implicito, gli sviluppatori potrebbero non essere consapevoli che sono la mutazione di copia e non il valore originale.</span><span class="sxs-lookup"><span data-stu-id="f75b6-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="f75b6-112">Inoltre, alcuni linguaggi (linguaggi dinamici, in particolare) verificarsi dei problemi con i tipi di valore modificabile perché anche le variabili locali, quando viene dereferenziato, provocare una copia da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f75b6-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="f75b6-113">**✓ SI** garantire che in uno stato in cui tutti i dati dell'istanza è impostato su zero, false o null (se necessario) è valido.</span><span class="sxs-lookup"><span data-stu-id="f75b6-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="f75b6-114">Ciò impedisce la creazione accidentale di istanze non valide quando viene creata una matrice di strutture.</span><span class="sxs-lookup"><span data-stu-id="f75b6-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="f75b6-115">**✓ SI** implementare <xref:System.IEquatable%601> sui tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="f75b6-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="f75b6-116">Il <xref:System.Object.Equals%2A?displayProperty=nameWithType> metodo nei tipi di valore determina la conversione boxing e l'implementazione predefinita non è molto efficiente, perché usa la reflection.</span><span class="sxs-lookup"><span data-stu-id="f75b6-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="f75b6-117"><xref:System.IEquatable%601.Equals%2A> può avere prestazioni migliori e può essere implementato in modo che non causa la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="f75b6-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="f75b6-118">**X non** estendere in modo esplicito <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="f75b6-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="f75b6-119">In effetti, la maggior parte dei linguaggi evitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="f75b6-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="f75b6-120">In generale, le strutture possono rivelarsi molto utile, ma devono essere utilizzate solo per i valori di piccole dimensioni, single, non modificabili che non essere boxed frequentemente.</span><span class="sxs-lookup"><span data-stu-id="f75b6-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="f75b6-121">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="f75b6-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f75b6-122">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f75b6-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75b6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f75b6-123">See Also</span></span>  
 [<span data-ttu-id="f75b6-124">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="f75b6-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="f75b6-125">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="f75b6-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="f75b6-126">Scelta tra classi e struct</span><span class="sxs-lookup"><span data-stu-id="f75b6-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
