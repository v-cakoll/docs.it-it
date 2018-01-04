---
title: Tipi annidati
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 389ba73c4509f41f6c2cf86363e59ea720eb3c9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="nested-types"></a><span data-ttu-id="37151-102">Tipi annidati</span><span class="sxs-lookup"><span data-stu-id="37151-102">Nested Types</span></span>
<span data-ttu-id="37151-103">Un tipo annidato è un tipo definito nell'ambito di un altro tipo, viene chiamato il tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="37151-103">A nested type is a type defined within the scope of another type, which is called the enclosing type.</span></span> <span data-ttu-id="37151-104">Un tipo annidato può accedere a tutti i membri del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="37151-104">A nested type has access to all members of its enclosing type.</span></span> <span data-ttu-id="37151-105">Ad esempio, ha accesso a campi privati definiti nel tipo di inclusione e proteggere i campi definiti in tutti i predecessori del tipo di inclusione.</span><span class="sxs-lookup"><span data-stu-id="37151-105">For example, it has access to private fields defined in the enclosing type and to protected fields defined in all ascendants of the enclosing type.</span></span>  
  
 <span data-ttu-id="37151-106">In generale, i tipi annidati devono essere usati con cautela.</span><span class="sxs-lookup"><span data-stu-id="37151-106">In general, nested types should be used sparingly.</span></span> <span data-ttu-id="37151-107">Le ragioni sono molteplici.</span><span class="sxs-lookup"><span data-stu-id="37151-107">There are several reasons for this.</span></span> <span data-ttu-id="37151-108">Alcuni sviluppatori non sono completamente familiarità con il concetto.</span><span class="sxs-lookup"><span data-stu-id="37151-108">Some developers are not fully familiar with the concept.</span></span> <span data-ttu-id="37151-109">Questi sviluppatori potrebbero, ad esempio, avere problemi con la sintassi di dichiarazione di variabili di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="37151-109">These developers might, for example, have problems with the syntax of declaring variables of nested types.</span></span> <span data-ttu-id="37151-110">Tipi annidati sono inoltre molto strettamente con i tipi di inclusione e di conseguenza non sono adatte per essere tipi generici.</span><span class="sxs-lookup"><span data-stu-id="37151-110">Nested types are also very tightly coupled with their enclosing types, and as such are not suited to be general-purpose types.</span></span>  
  
 <span data-ttu-id="37151-111">I tipi annidati sono particolarmente adatti per la modellazione dei dettagli di implementazione dei relativi tipi di inclusione.</span><span class="sxs-lookup"><span data-stu-id="37151-111">Nested types are best suited for modeling implementation details of their enclosing types.</span></span> <span data-ttu-id="37151-112">L'utente finale deve raramente è necessario dichiarare le variabili di un tipo annidato e quasi mai necessario creare un'istanza esplicita di tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="37151-112">The end user should rarely have to declare variables of a nested type and almost never should have to explicitly instantiate nested types.</span></span> <span data-ttu-id="37151-113">Ad esempio, l'enumeratore di una raccolta può essere un tipo annidato di tale raccolta.</span><span class="sxs-lookup"><span data-stu-id="37151-113">For example, the enumerator of a collection can be a nested type of that collection.</span></span> <span data-ttu-id="37151-114">Gli enumeratori sono in genere creata un'istanza in base al tipo di inclusione e poiché molti linguaggi supportano l'istruzione foreach, le variabili di enumeratore raramente devono essere dichiarati dall'utente finale.</span><span class="sxs-lookup"><span data-stu-id="37151-114">Enumerators are usually instantiated by their enclosing type, and because many languages support the foreach statement, enumerator variables rarely have to be declared by the end user.</span></span>  
  
 <span data-ttu-id="37151-115">**✓ SI** utilizzare tipi annidati tale semantica di accessibilità di membri è utile quando la relazione tra il tipo annidato e il relativo tipo esterno.</span><span class="sxs-lookup"><span data-stu-id="37151-115">**✓ DO** use nested types when the relationship between the nested type and its outer type is such that member-accessibility semantics are desirable.</span></span>  
  
 <span data-ttu-id="37151-116">**X non** utilizzare tipi annidati pubblici come un raggruppamento logico di costruire; utilizzare gli spazi dei nomi per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="37151-116">**X DO NOT** use public nested types as a logical grouping construct; use namespaces for this.</span></span>  
  
 <span data-ttu-id="37151-117">**X evitare** esposte pubblicamente tipi annidati.</span><span class="sxs-lookup"><span data-stu-id="37151-117">**X AVOID** publicly exposed nested types.</span></span> <span data-ttu-id="37151-118">L'unica eccezione è se è necessario essere dichiarati solo in rari scenari, ad esempio la creazione di sottoclassi o altri scenari di personalizzazione avanzate variabili del tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="37151-118">The only exception to this is if variables of the nested type need to be declared only in rare scenarios such as subclassing or other advanced customization scenarios.</span></span>  
  
 <span data-ttu-id="37151-119">**X non** utilizzare tipi annidati, se il tipo è probabile che venga fatto riferimento all'esterno del tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="37151-119">**X DO NOT** use nested types if the type is likely to be referenced outside of the containing type.</span></span>  
  
 <span data-ttu-id="37151-120">Ad esempio, un'enumerazione passata a un metodo definito in una classe non deve essere definita come un tipo annidato nella classe.</span><span class="sxs-lookup"><span data-stu-id="37151-120">For example, an enum passed to a method defined on a class should not be defined as a nested type in the class.</span></span>  
  
 <span data-ttu-id="37151-121">**X non** utilizzare tipi annidati, se è necessario creare un'istanza dal codice client.</span><span class="sxs-lookup"><span data-stu-id="37151-121">**X DO NOT** use nested types if they need to be instantiated by client code.</span></span>  <span data-ttu-id="37151-122">Se un tipo ha un costruttore pubblico, probabilmente non si devono nidificato.</span><span class="sxs-lookup"><span data-stu-id="37151-122">If a type has a public constructor, it should probably not be nested.</span></span>  
  
 <span data-ttu-id="37151-123">Se è possibile creare istanze di un tipo, può sembrare per indicare il tipo ha una posizione nel framework autonomamente (è possibile crearlo, lavorare con esso ed eliminato senza mai utilizzare il tipo esterno) e pertanto non devono essere nidificate.</span><span class="sxs-lookup"><span data-stu-id="37151-123">If a type can be instantiated, that seems to indicate the type has a place in the framework on its own (you can create it, work with it, and destroy it without ever using the outer type), and thus should not be nested.</span></span> <span data-ttu-id="37151-124">Tipi interni non devono essere riutilizzati ampiamente all'esterno del tipo outer senza alcuna relazione verso il tipo esterno.</span><span class="sxs-lookup"><span data-stu-id="37151-124">Inner types should not be widely reused outside of the outer type without any relationship whatsoever to the outer type.</span></span>  
  
 <span data-ttu-id="37151-125">**X non** definire un tipo annidato come membro di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="37151-125">**X DO NOT** define a nested type as a member of an interface.</span></span> <span data-ttu-id="37151-126">Molti linguaggi non supportano tale costrutto.</span><span class="sxs-lookup"><span data-stu-id="37151-126">Many languages do not support such a construct.</span></span>  
  
 <span data-ttu-id="37151-127">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="37151-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="37151-128">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="37151-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37151-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37151-129">See Also</span></span>  
 [<span data-ttu-id="37151-130">Linee guida per la progettazione di tipi</span><span class="sxs-lookup"><span data-stu-id="37151-130">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="37151-131">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="37151-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
