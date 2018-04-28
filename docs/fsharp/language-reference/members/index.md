---
title: Membri (F#)
description: Informazioni sui membri di oggetto nel linguaggio di programmazione c#.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a37f14d138cc017cf78e3a0ff1d5b5bba2f09020
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="members"></a><span data-ttu-id="07aad-103">Membri</span><span class="sxs-lookup"><span data-stu-id="07aad-103">Members</span></span>

<span data-ttu-id="07aad-104">Questa sezione illustra i membri dei tipi di oggetto F#.</span><span class="sxs-lookup"><span data-stu-id="07aad-104">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="07aad-105">Note</span><span class="sxs-lookup"><span data-stu-id="07aad-105">Remarks</span></span>
<span data-ttu-id="07aad-106">I *membri* sono funzionalità che fanno parte di una definizione di tipo e vengono dichiarati con la parola chiave `member`.</span><span class="sxs-lookup"><span data-stu-id="07aad-106">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="07aad-107">I tipi di oggetto F#, ad esempio record, classi, unioni discriminate, interfacce e strutture, supportano i membri.</span><span class="sxs-lookup"><span data-stu-id="07aad-107">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="07aad-108">Per altre informazioni, vedere [Record](../records.md), [Classi](../classes.md), [Unioni discriminate](../discriminated-Unions.md), [Interfacce](../interfaces.md) e [Strutture](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="07aad-108">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="07aad-109">I membri in genere costituiscono l'interfaccia pubblica per un tipo, e per questo motivo sono pubblici, se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="07aad-109">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="07aad-110">I membri possono anche essere dichiarati privati o interni.</span><span class="sxs-lookup"><span data-stu-id="07aad-110">Members can also be declared private or internal.</span></span> <span data-ttu-id="07aad-111">Per altre informazioni, vedere [Controllo di accesso](../access-Control.md).</span><span class="sxs-lookup"><span data-stu-id="07aad-111">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="07aad-112">Le firme per i tipi possono anche essere usate per esporre o meno determinati membri di un tipo.</span><span class="sxs-lookup"><span data-stu-id="07aad-112">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="07aad-113">Per altre informazioni, vedere [Firme](../signatures.md).</span><span class="sxs-lookup"><span data-stu-id="07aad-113">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="07aad-114">I campi privati e le associazioni `do`, usati solo con le classi, non sono membri veri, perché non fanno mai parte dell'interfaccia pubblica di un tipo e non sono dichiarati con la parola chiave `member`, però vengono descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="07aad-114">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="07aad-115">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="07aad-115">Related Topics</span></span>


|<span data-ttu-id="07aad-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="07aad-116">Topic</span></span>|<span data-ttu-id="07aad-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07aad-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="07aad-118">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="07aad-118">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="07aad-119">Descrive la definizione dei campi privati e le funzioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="07aad-119">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="07aad-120">Associazioni `do` nelle classi</span><span class="sxs-lookup"><span data-stu-id="07aad-120">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="07aad-121">Descrive la specifica del codice di inizializzazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="07aad-121">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="07aad-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="07aad-122">Properties</span></span>](properties.md)|<span data-ttu-id="07aad-123">Descrive i membri di proprietà nelle classi e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="07aad-123">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="07aad-124">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="07aad-124">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="07aad-125">Descrive le proprietà di tipo matrice nelle classi e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="07aad-125">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="07aad-126">Metodi</span><span class="sxs-lookup"><span data-stu-id="07aad-126">Methods</span></span>](methods.md)|<span data-ttu-id="07aad-127">Descrive funzioni che sono membri di un tipo.</span><span class="sxs-lookup"><span data-stu-id="07aad-127">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="07aad-128">Costruttori</span><span class="sxs-lookup"><span data-stu-id="07aad-128">Constructors</span></span>](constructors.md)|<span data-ttu-id="07aad-129">Descrive funzioni speciali che inizializzano oggetti di un tipo.</span><span class="sxs-lookup"><span data-stu-id="07aad-129">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="07aad-130">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="07aad-130">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="07aad-131">Descrive la definizione di operatori personalizzati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="07aad-131">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="07aad-132">Eventi</span><span class="sxs-lookup"><span data-stu-id="07aad-132">Events</span></span>](events.md)|<span data-ttu-id="07aad-133">Descrive la definizione di eventi e il supporto di gestione degli eventi in F# .</span><span class="sxs-lookup"><span data-stu-id="07aad-133">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="07aad-134">Campi espliciti: parola chiave `val`</span><span class="sxs-lookup"><span data-stu-id="07aad-134">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="07aad-135">Descrive la definizione dei campi non inizializzati in un tipo.</span><span class="sxs-lookup"><span data-stu-id="07aad-135">Describes the definition of uninitialized fields in a type.</span></span>|
