---
title: Modificatori (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- keywords [C#], modifiers
- modifiers [C#]
ms.assetid: c96691dd-b357-49ec-b5ae-03ca214fadfb
caps.latest.revision: 18
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
ms.openlocfilehash: 9e2e7e5e3907ac9bb66676e749ddd55a8ac4836c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="modifiers-c-reference"></a><span data-ttu-id="559af-102">Modificatori (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="559af-102">Modifiers (C# Reference)</span></span>
<span data-ttu-id="559af-103">I modificatori vengono utilizzati per modificare le dichiarazioni dei tipi e dei membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="559af-103">Modifiers are used to modify declarations of types and type members.</span></span> <span data-ttu-id="559af-104">In questa sezione verranno descritti i modificatori C#.</span><span class="sxs-lookup"><span data-stu-id="559af-104">This section introduces the C# modifiers.</span></span>  
  
|<span data-ttu-id="559af-105">Modificatore</span><span class="sxs-lookup"><span data-stu-id="559af-105">Modifier</span></span>|<span data-ttu-id="559af-106">Scopo</span><span class="sxs-lookup"><span data-stu-id="559af-106">Purpose</span></span>|  
|--------------|-------------|  
|[<span data-ttu-id="559af-107">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="559af-107">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)<br /><br /> <span data-ttu-id="559af-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span><span class="sxs-lookup"><span data-stu-id="559af-108">-   [public](../../../csharp/language-reference/keywords/public.md)</span></span><br /><span data-ttu-id="559af-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span><span class="sxs-lookup"><span data-stu-id="559af-109">-   [private](../../../csharp/language-reference/keywords/private.md)</span></span><br /><span data-ttu-id="559af-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span><span class="sxs-lookup"><span data-stu-id="559af-110">-   [internal](../../../csharp/language-reference/keywords/internal.md)</span></span><br /><span data-ttu-id="559af-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span><span class="sxs-lookup"><span data-stu-id="559af-111">-   [protected](../../../csharp/language-reference/keywords/protected.md)</span></span>|<span data-ttu-id="559af-112">Specifica l'accessibilità dichiarata dei tipi e dei membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="559af-112">Specifies the declared accessibility of types and type members.</span></span>|  
|[<span data-ttu-id="559af-113">abstract</span><span class="sxs-lookup"><span data-stu-id="559af-113">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="559af-114">Indica che una classe può essere utilizzata solo come classe base di altre classi.</span><span class="sxs-lookup"><span data-stu-id="559af-114">Indicates that a class is intended only to be a base class of other classes.</span></span>|  
|[<span data-ttu-id="559af-115">async</span><span class="sxs-lookup"><span data-stu-id="559af-115">async</span></span>](../../../csharp/language-reference/keywords/async.md)|<span data-ttu-id="559af-116">Indica che il metodo specificato, l'espressione lambda o il metodo anonimo è asincrono.</span><span class="sxs-lookup"><span data-stu-id="559af-116">Indicates that the modified method, lambda expression, or anonymous method is asynchronous.</span></span>|  
|[<span data-ttu-id="559af-117">const</span><span class="sxs-lookup"><span data-stu-id="559af-117">const</span></span>](../../../csharp/language-reference/keywords/const.md)|<span data-ttu-id="559af-118">Specifica che non è possibile modificare il valore del campo o della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="559af-118">Specifies that the value of the field or the local variable cannot be modified.</span></span>|  
|[<span data-ttu-id="559af-119">event</span><span class="sxs-lookup"><span data-stu-id="559af-119">event</span></span>](../../../csharp/language-reference/keywords/event.md)|<span data-ttu-id="559af-120">Dichiara un evento.</span><span class="sxs-lookup"><span data-stu-id="559af-120">Declares an event.</span></span>|  
|[<span data-ttu-id="559af-121">extern</span><span class="sxs-lookup"><span data-stu-id="559af-121">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)|<span data-ttu-id="559af-122">Indica che il metodo viene implementato esternamente.</span><span class="sxs-lookup"><span data-stu-id="559af-122">Indicates that the method is implemented externally.</span></span>|  
|[<span data-ttu-id="559af-123">new</span><span class="sxs-lookup"><span data-stu-id="559af-123">new</span></span>](../../../csharp/language-reference/keywords/new.md)|<span data-ttu-id="559af-124">Nasconde in modo esplicito un membro ereditato da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="559af-124">Explicitly hides a member inherited from a base class.</span></span>|  
|[<span data-ttu-id="559af-125">override</span><span class="sxs-lookup"><span data-stu-id="559af-125">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="559af-126">Fornisce una nuova implementazione di un membro virtuale ereditato da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="559af-126">Provides a new implementation of a virtual member inherited from a base class.</span></span>|  
|[<span data-ttu-id="559af-127">partial</span><span class="sxs-lookup"><span data-stu-id="559af-127">partial</span></span>](../../../csharp/language-reference/keywords/partial-type.md)|<span data-ttu-id="559af-128">Definisce classi, struct e metodi parziali all'interno dello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="559af-128">Defines partial classes, structs and methods throughout the same assembly.</span></span>|  
|[<span data-ttu-id="559af-129">readonly</span><span class="sxs-lookup"><span data-stu-id="559af-129">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)|<span data-ttu-id="559af-130">Dichiara un campo al quale è possibile assegnare valori solo come parte della dichiarazione o in un costruttore della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="559af-130">Declares a field that can only be assigned values as part of the declaration or in a constructor in the same class.</span></span>|  
|[<span data-ttu-id="559af-131">sealed</span><span class="sxs-lookup"><span data-stu-id="559af-131">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="559af-132">Specifica che la classe non può essere ereditata.</span><span class="sxs-lookup"><span data-stu-id="559af-132">Specifies that a class cannot be inherited.</span></span>|  
|[<span data-ttu-id="559af-133">static</span><span class="sxs-lookup"><span data-stu-id="559af-133">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="559af-134">Dichiara un membro che appartiene al tipo stesso anziché a un oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="559af-134">Declares a member that belongs to the type itself instead of to a specific object.</span></span>|  
|[<span data-ttu-id="559af-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="559af-135">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)|<span data-ttu-id="559af-136">Dichiara un contesto non sicuro.</span><span class="sxs-lookup"><span data-stu-id="559af-136">Declares an unsafe context.</span></span>|  
|[<span data-ttu-id="559af-137">virtual</span><span class="sxs-lookup"><span data-stu-id="559af-137">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="559af-138">Dichiara un metodo o una funzione di accesso la cui implementazione può essere modificata da un membro in override di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="559af-138">Declares a method or an accessor whose implementation can be changed by an overriding member in a derived class.</span></span>|  
|[<span data-ttu-id="559af-139">volatile</span><span class="sxs-lookup"><span data-stu-id="559af-139">volatile</span></span>](../../../csharp/language-reference/keywords/volatile.md)|<span data-ttu-id="559af-140">Indica che un campo all'interno del programma può essere modificato dal sistema operativo, da un componente hardware oppure da un thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="559af-140">Indicates that a field can be modified in the program by something such as the operating system, the hardware, or a concurrently executing thread.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="559af-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="559af-141">See Also</span></span>  
 <span data-ttu-id="559af-142">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="559af-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="559af-143">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="559af-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="559af-144">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="559af-144">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

