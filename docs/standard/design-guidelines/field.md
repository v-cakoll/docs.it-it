---
title: Progettazione di campi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65c54fe9a076a219c61280a98c390b16f56b5015
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43873942"
---
# <a name="field-design"></a><span data-ttu-id="3384c-102">Progettazione di campi</span><span class="sxs-lookup"><span data-stu-id="3384c-102">Field Design</span></span>
<span data-ttu-id="3384c-103">Il principio di incapsulamento è uno dei concetti più importanti nella progettazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3384c-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="3384c-104">Questo principio specifica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="3384c-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="3384c-105">Un modo utile per interpretare il principio è dire che un tipo deve essere progettato in modo che le modifiche apportate ai campi di quel tipo (modifiche di nome o tipo) possono essere eseguite senza causare interruzioni nel codice diverso per i membri del tipo.</span><span class="sxs-lookup"><span data-stu-id="3384c-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="3384c-106">Questa interpretazione immediatamente significa che tutti i campi devono essere privati.</span><span class="sxs-lookup"><span data-stu-id="3384c-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="3384c-107">Microsoft esclude statici e costanti campi di sola lettura da questa limitazione strict, in quanto tali campi, quasi per definizione, non sono mai richiesto di modificare.</span><span class="sxs-lookup"><span data-stu-id="3384c-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="3384c-108">**X DO NOT** forniscono i campi di istanza pubblici sono protetti.</span><span class="sxs-lookup"><span data-stu-id="3384c-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="3384c-109">È necessario fornire le proprietà per l'accesso ai campi anziché rendendoli pubblico o protetto.</span><span class="sxs-lookup"><span data-stu-id="3384c-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="3384c-110">**✓ DO** utilizzare i campi costanti per le costanti che non verranno mai modificato.</span><span class="sxs-lookup"><span data-stu-id="3384c-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="3384c-111">Il compilatore esegue il burn-i valori dei campi const direttamente nella chiamata di codice.</span><span class="sxs-lookup"><span data-stu-id="3384c-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="3384c-112">Pertanto, valori const non possono mai essere modificati senza il rischio di compromettere la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="3384c-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="3384c-113">**✓ DO** utilizzare statici pubblici `readonly` campi per le istanze di oggetto predefinito.</span><span class="sxs-lookup"><span data-stu-id="3384c-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="3384c-114">Se sono presenti istanze predefinite del tipo, dichiararli come public campi statici di sola lettura del tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="3384c-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="3384c-115">**X DO NOT** assegna le istanze di tipi modificabili per `readonly` campi.</span><span class="sxs-lookup"><span data-stu-id="3384c-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="3384c-116">Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="3384c-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="3384c-117">Ad esempio, matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, e <xref:System.String?displayProperty=nameWithType> sono tutti modificabili.</span><span class="sxs-lookup"><span data-stu-id="3384c-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="3384c-118">Il modificatore di sola lettura su un campo di tipo riferimento impedisce l'istanza archiviato nel campo venga sostituito, ma non impedisce che i dati dell'istanza del campo vengano modificati chiamando i membri di modifica dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3384c-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="3384c-119">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3384c-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3384c-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3384c-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3384c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3384c-121">See also</span></span>

- [<span data-ttu-id="3384c-122">Linee guida di progettazione dei membri</span><span class="sxs-lookup"><span data-stu-id="3384c-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="3384c-123">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3384c-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
