---
title: Membri (F#)
description: Informazioni sui membri di oggetto nel linguaggio di programmazione c#.
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a><span data-ttu-id="6f245-104">Membri</span><span class="sxs-lookup"><span data-stu-id="6f245-104">Members</span></span>

<span data-ttu-id="6f245-105">Questa sezione illustra i membri dei tipi di oggetto F#.</span><span class="sxs-lookup"><span data-stu-id="6f245-105">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="6f245-106">Note</span><span class="sxs-lookup"><span data-stu-id="6f245-106">Remarks</span></span>
<span data-ttu-id="6f245-107">I *membri* sono funzionalità che fanno parte di una definizione di tipo e vengono dichiarati con la parola chiave `member`.</span><span class="sxs-lookup"><span data-stu-id="6f245-107">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="6f245-108">I tipi di oggetto F#, ad esempio record, classi, unioni discriminate, interfacce e strutture, supportano i membri.</span><span class="sxs-lookup"><span data-stu-id="6f245-108">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="6f245-109">Per altre informazioni, vedere [Record](../records.md), [Classi](../classes.md), [Unioni discriminate](../discriminated-Unions.md), [Interfacce](../interfaces.md) e [Strutture](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="6f245-109">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="6f245-110">I membri in genere costituiscono l'interfaccia pubblica per un tipo, e per questo motivo sono pubblici, se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="6f245-110">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="6f245-111">I membri possono anche essere dichiarati privati o interni.</span><span class="sxs-lookup"><span data-stu-id="6f245-111">Members can also be declared private or internal.</span></span> <span data-ttu-id="6f245-112">Per altre informazioni, vedere [Controllo di accesso](../access-Control.md).</span><span class="sxs-lookup"><span data-stu-id="6f245-112">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="6f245-113">Le firme per i tipi possono anche essere usate per esporre o meno determinati membri di un tipo.</span><span class="sxs-lookup"><span data-stu-id="6f245-113">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="6f245-114">Per altre informazioni, vedere [Firme](../signatures.md).</span><span class="sxs-lookup"><span data-stu-id="6f245-114">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="6f245-115">I campi privati e le associazioni `do`, usati solo con le classi, non sono membri veri, perché non fanno mai parte dell'interfaccia pubblica di un tipo e non sono dichiarati con la parola chiave `member`, però vengono descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="6f245-115">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6f245-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6f245-116">Related Topics</span></span>


|<span data-ttu-id="6f245-117">Argomento</span><span class="sxs-lookup"><span data-stu-id="6f245-117">Topic</span></span>|<span data-ttu-id="6f245-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f245-118">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="6f245-119">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="6f245-119">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)|<span data-ttu-id="6f245-120">Descrive la definizione dei campi privati e le funzioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="6f245-120">Describes the definition of private fields and functions in classes.</span></span>|
|[<span data-ttu-id="6f245-121">Associazioni `do` nelle classi</span><span class="sxs-lookup"><span data-stu-id="6f245-121">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)|<span data-ttu-id="6f245-122">Descrive la specifica del codice di inizializzazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6f245-122">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="6f245-123">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6f245-123">Properties</span></span>](properties.md)|<span data-ttu-id="6f245-124">Descrive i membri di proprietà nelle classi e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="6f245-124">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="6f245-125">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="6f245-125">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="6f245-126">Descrive le proprietà di tipo matrice nelle classi e altri tipi.</span><span class="sxs-lookup"><span data-stu-id="6f245-126">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="6f245-127">Metodi</span><span class="sxs-lookup"><span data-stu-id="6f245-127">Methods</span></span>](methods.md)|<span data-ttu-id="6f245-128">Descrive funzioni che sono membri di un tipo.</span><span class="sxs-lookup"><span data-stu-id="6f245-128">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="6f245-129">Costruttori</span><span class="sxs-lookup"><span data-stu-id="6f245-129">Constructors</span></span>](constructors.md)|<span data-ttu-id="6f245-130">Descrive funzioni speciali che inizializzano oggetti di un tipo.</span><span class="sxs-lookup"><span data-stu-id="6f245-130">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="6f245-131">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="6f245-131">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="6f245-132">Descrive la definizione di operatori personalizzati per i tipi.</span><span class="sxs-lookup"><span data-stu-id="6f245-132">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="6f245-133">Eventi</span><span class="sxs-lookup"><span data-stu-id="6f245-133">Events</span></span>](events.md)|<span data-ttu-id="6f245-134">Descrive la definizione di eventi e il supporto di gestione degli eventi in F# .</span><span class="sxs-lookup"><span data-stu-id="6f245-134">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="6f245-135">Campi espliciti: parola chiave `val`</span><span class="sxs-lookup"><span data-stu-id="6f245-135">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="6f245-136">Descrive la definizione dei campi non inizializzati in un tipo.</span><span class="sxs-lookup"><span data-stu-id="6f245-136">Describes the definition of uninitialized fields in a type.</span></span>|
