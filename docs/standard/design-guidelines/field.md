---
title: Progettazione di campi
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 3a5ae985ab161899fbb5e96f9b0ef0cfa90b957c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289746"
---
# <a name="field-design"></a><span data-ttu-id="d9cb6-102">Progettazione di campi</span><span class="sxs-lookup"><span data-stu-id="d9cb6-102">Field Design</span></span>
<span data-ttu-id="d9cb6-103">Il principio di incapsulamento è uno dei concetti più importanti della progettazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="d9cb6-104">Questo principio indica che i dati archiviati all'interno di un oggetto devono essere accessibili solo a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="d9cb6-105">Un modo utile per interpretare il principio è quello di indicare che un tipo deve essere progettato in modo che sia possibile apportare modifiche ai campi di quel tipo (nome o tipo) senza suddividere il codice per i membri del tipo.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="d9cb6-106">Questa interpretazione implica immediatamente che tutti i campi debbano essere privati.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-106">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="d9cb6-107">Si escludono i campi costanti e statici di sola lettura da questa restrizione restrittiva, perché tali campi, quasi per definizione, non sono mai necessari per la modifica.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="d9cb6-108">❌Non specificare campi di istanza pubblici o protetti.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-108">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="d9cb6-109">È necessario specificare le proprietà per l'accesso ai campi, anziché renderle pubbliche o protette.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="d9cb6-110">✔️ utilizzano campi costanti per le costanti che non vengono mai modificate.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-110">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="d9cb6-111">Il compilatore brucia i valori dei campi const direttamente nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="d9cb6-112">Pertanto, i valori const non possono mai essere modificati senza il rischio di interruzioni della compatibilità.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="d9cb6-113">✔️ usare campi statici pubblici `readonly` per le istanze di oggetti predefinite.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-113">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="d9cb6-114">Se sono presenti istanze predefinite del tipo, dichiararle come campi statici di sola lettura pubblici del tipo stesso.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="d9cb6-115">❌NON assegnare istanze di tipi modificabili ai `readonly` campi.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-115">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="d9cb6-116">Un tipo modificabile è un tipo con istanze che possono essere modificate dopo la creazione di istanze.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="d9cb6-117">Ad esempio, le matrici, la maggior parte delle raccolte e i flussi sono tipi modificabili, ma <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> e <xref:System.String?displayProperty=nameWithType> sono tutti non modificabili.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="d9cb6-118">Il modificatore di sola lettura in un campo di tipo riferimento impedisce che l'istanza archiviata nel campo venga sostituita, ma non impedisce la modifica dei dati dell'istanza del campo chiamando membri che modificano l'istanza.</span><span class="sxs-lookup"><span data-stu-id="d9cb6-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="d9cb6-119">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="d9cb6-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="d9cb6-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="d9cb6-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="d9cb6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9cb6-121">See also</span></span>

- [<span data-ttu-id="d9cb6-122">Linee guida per la progettazione di membri</span><span class="sxs-lookup"><span data-stu-id="d9cb6-122">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="d9cb6-123">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="d9cb6-123">Framework Design Guidelines</span></span>](index.md)
