---
title: Progettazione di struct
ms.date: 10/22/2008
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
ms.openlocfilehash: b6d06bc8a1e8535f1452af0726138abaebfd4951
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743608"
---
# <a name="struct-design"></a><span data-ttu-id="a82d2-102">Progettazione di struct</span><span class="sxs-lookup"><span data-stu-id="a82d2-102">Struct Design</span></span>
<span data-ttu-id="a82d2-103">Il tipo di valore di utilizzo generico è spesso definito struct, la relativa C# parola chiave.</span><span class="sxs-lookup"><span data-stu-id="a82d2-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="a82d2-104">Questa sezione fornisce linee guida per la progettazione di struct generali.</span><span class="sxs-lookup"><span data-stu-id="a82d2-104">This section provides guidelines for general struct design.</span></span>

 <span data-ttu-id="a82d2-105">❌ non forniscono un costruttore senza parametri per uno struct.</span><span class="sxs-lookup"><span data-stu-id="a82d2-105">❌ DO NOT provide a parameterless constructor for a struct.</span></span>

 <span data-ttu-id="a82d2-106">Seguendo questa guida, è possibile creare matrici di struct senza dover eseguire il costruttore in ogni elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="a82d2-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="a82d2-107">Si noti C# che non consente agli struct di avere costruttori senza parametri.</span><span class="sxs-lookup"><span data-stu-id="a82d2-107">Notice that C# does not allow structs to have parameterless constructors.</span></span>

 <span data-ttu-id="a82d2-108">❌ non definiscono tipi di valore modificabili.</span><span class="sxs-lookup"><span data-stu-id="a82d2-108">❌ DO NOT define mutable value types.</span></span>

 <span data-ttu-id="a82d2-109">I tipi di valore modificabili presentano diversi problemi.</span><span class="sxs-lookup"><span data-stu-id="a82d2-109">Mutable value types have several problems.</span></span> <span data-ttu-id="a82d2-110">Ad esempio, quando un getter di proprietà restituisce un tipo di valore, il chiamante riceve una copia.</span><span class="sxs-lookup"><span data-stu-id="a82d2-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="a82d2-111">Poiché la copia viene creata in modo implicito, è possibile che gli sviluppatori non ritengano che stiano mutando la copia e non il valore originale.</span><span class="sxs-lookup"><span data-stu-id="a82d2-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="a82d2-112">Inoltre, alcune lingue (linguaggi dinamici, in particolare) presentano problemi con i tipi di valore modificabili perché anche le variabili locali, quando vengono dereferenziate, causano la copia.</span><span class="sxs-lookup"><span data-stu-id="a82d2-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>

 <span data-ttu-id="a82d2-113">✔️ Verificare che uno stato in cui tutti i dati dell'istanza siano impostati su zero, false o null (se appropriato) sia valido.</span><span class="sxs-lookup"><span data-stu-id="a82d2-113">✔️ DO ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>

 <span data-ttu-id="a82d2-114">Ciò impedisce la creazione accidentale di istanze non valide quando viene creata una matrice degli struct.</span><span class="sxs-lookup"><span data-stu-id="a82d2-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>

 <span data-ttu-id="a82d2-115">✔️ implementano <xref:System.IEquatable%601> sui tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="a82d2-115">✔️ DO implement <xref:System.IEquatable%601> on value types.</span></span>

 <span data-ttu-id="a82d2-116">Il <xref:System.Object.Equals%2A?displayProperty=nameWithType> metodo sui tipi valore causa la conversione boxing e la relativa implementazione predefinita non è molto efficiente, perché usa la reflection.</span><span class="sxs-lookup"><span data-stu-id="a82d2-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="a82d2-117"><xref:System.IEquatable%601.Equals%2A> possono avere prestazioni molto migliori e possono essere implementate in modo che non provochino la conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="a82d2-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>

 <span data-ttu-id="a82d2-118">❌ non estendono esplicitamente <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="a82d2-118">❌ DO NOT explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="a82d2-119">In realtà, la maggior parte dei linguaggi impedisce questo problema.</span><span class="sxs-lookup"><span data-stu-id="a82d2-119">In fact, most languages prevent this.</span></span>

 <span data-ttu-id="a82d2-120">In generale, gli struct possono essere molto utili, ma devono essere usati solo per valori piccoli, singoli e non modificabili che non verranno sottoposto a Boxing di frequente.</span><span class="sxs-lookup"><span data-stu-id="a82d2-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>

 <span data-ttu-id="a82d2-121">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="a82d2-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="a82d2-122">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a82d2-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="a82d2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a82d2-123">See also</span></span>

- [<span data-ttu-id="a82d2-124">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="a82d2-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="a82d2-125">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="a82d2-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="a82d2-126">Scelta tra classi e struct</span><span class="sxs-lookup"><span data-stu-id="a82d2-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
