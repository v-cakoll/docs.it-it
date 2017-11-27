---
title: 'Campi espliciti: parola chiave val (F#)'
description: 'Informazioni su F # ''val'' parola chiave, che viene utilizzata per dichiarare un percorso per archiviare un valore in un tipo classe o struttura senza inizializzare il tipo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3bdbc745-436b-407f-bf54-5d11ca829cd0
ms.openlocfilehash: cee53a48f08aec89b0bdd40189ed331cadee877d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="explicit-fields-the-val-keyword"></a><span data-ttu-id="dd701-104">Campi espliciti: parola chiave val</span><span class="sxs-lookup"><span data-stu-id="dd701-104">Explicit Fields: The val Keyword</span></span>

<span data-ttu-id="dd701-105">La parola chiave `val` viene usata per dichiarare un percorso per archiviare un valore in un tipo di classe o struttura senza inizializzarlo.</span><span class="sxs-lookup"><span data-stu-id="dd701-105">The `val` keyword is used to declare a location to store a value in a class or structure type, without initializing it.</span></span> <span data-ttu-id="dd701-106">Percorsi di archiviazione dichiarati in questo modo vengono chiamati *campi espliciti*.</span><span class="sxs-lookup"><span data-stu-id="dd701-106">Storage locations declared in this manner are called *explicit fields*.</span></span> <span data-ttu-id="dd701-107">Un altro uso della parola chiave `val` è in combinazione con la parola chiave `member` per dichiarare una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dd701-107">Another use of the `val` keyword is in conjunction with the `member` keyword to declare an auto-implemented property.</span></span> <span data-ttu-id="dd701-108">Per ulteriori informazioni sulle proprietà implementate automaticamente, vedere [proprietà](properties.md).</span><span class="sxs-lookup"><span data-stu-id="dd701-108">For more information on auto-implemented properties, see [Properties](properties.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="dd701-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd701-109">Syntax</span></span>

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a><span data-ttu-id="dd701-110">Note</span><span class="sxs-lookup"><span data-stu-id="dd701-110">Remarks</span></span>
<span data-ttu-id="dd701-111">La modalità standard per definire i campi in un tipo di classe o struttura consiste nell'usare un'associazione `let`.</span><span class="sxs-lookup"><span data-stu-id="dd701-111">The usual way to define fields in a class or structure type is to use a `let` binding.</span></span> <span data-ttu-id="dd701-112">Tuttavia, le associazioni `let` devono essere inizializzate come parte del costruttore della classe, ma non è sempre possibile, necessario o appropriato.</span><span class="sxs-lookup"><span data-stu-id="dd701-112">However, `let` bindings must be initialized as part of the class constructor, which is not always possible, necessary, or desirable.</span></span> <span data-ttu-id="dd701-113">È possibile usare la parola chiave `val` quando si desidera un campo non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="dd701-113">You can use the `val` keyword when you want a field that is uninitialized.</span></span>

<span data-ttu-id="dd701-114">I campi espliciti possono essere statici o non statici.</span><span class="sxs-lookup"><span data-stu-id="dd701-114">Explicit fields can be static or non-static.</span></span> <span data-ttu-id="dd701-115">Il *modificatore di accesso* può essere `public`, `private`, o `internal`.</span><span class="sxs-lookup"><span data-stu-id="dd701-115">The *access-modifier* can be `public`, `private`, or `internal`.</span></span> <span data-ttu-id="dd701-116">Per impostazione predefinita, i campi espliciti sono pubblici.</span><span class="sxs-lookup"><span data-stu-id="dd701-116">By default, explicit fields are public.</span></span> <span data-ttu-id="dd701-117">Questo comportamento è diverso dalle associazioni `let` nelle classi, che invece sono sempre private.</span><span class="sxs-lookup"><span data-stu-id="dd701-117">This differs from `let` bindings in classes, which are always private.</span></span>

<span data-ttu-id="dd701-118">Il [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attributo è obbligatorio nei campi espliciti nei tipi di classe che dispone di un costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="dd701-118">The [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attribute is required on explicit fields in class types that have a primary constructor.</span></span> <span data-ttu-id="dd701-119">Questo attributo specifica che il campo viene inizializzato su zero.</span><span class="sxs-lookup"><span data-stu-id="dd701-119">This attribute specifies that the field is initialized to zero.</span></span> <span data-ttu-id="dd701-120">Il tipo del campo deve supportare l'inizializzazione su zero.</span><span class="sxs-lookup"><span data-stu-id="dd701-120">The type of the field must support zero-initialization.</span></span> <span data-ttu-id="dd701-121">Un tipo supporta l'inizializzazione su zero se corrisponde a uno dei seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="dd701-121">A type supports zero-initialization if it is one of the following:</span></span>

- <span data-ttu-id="dd701-122">Un tipo primitivo con valore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="dd701-122">A primitive type that has a zero value.</span></span>

- <span data-ttu-id="dd701-123">Un tipo che supporta un valore null come valore normale, come valore anomalo o come rappresentazione di un valore.</span><span class="sxs-lookup"><span data-stu-id="dd701-123">A type that supports a null value, either as a normal value, as an abnormal value, or as a representation of a value.</span></span> <span data-ttu-id="dd701-124">Questo include classi, tuple, record, funzioni, interfacce, tipi di riferimento .NET, il tipo `unit` e i tipi di unioni discriminati.</span><span class="sxs-lookup"><span data-stu-id="dd701-124">This includes classes, tuples, records, functions, interfaces, .NET reference types, the `unit` type, and discriminated union types.</span></span>

- <span data-ttu-id="dd701-125">Un tipo di valore .NET.</span><span class="sxs-lookup"><span data-stu-id="dd701-125">A .NET value type.</span></span>

- <span data-ttu-id="dd701-126">Una struttura in cui tutti i campi supportano un valore predefinito pari a zero.</span><span class="sxs-lookup"><span data-stu-id="dd701-126">A structure whose fields all support a default zero value.</span></span>


<span data-ttu-id="dd701-127">Ad esempio, un campo non modificabile chiamato `someField` è un campo di supporto nella rappresentazione compilata .NET con il nome `someField@` e si accede al valore archiviato usando una proprietà denominata `someField`.</span><span class="sxs-lookup"><span data-stu-id="dd701-127">For example, an immutable field called `someField` has a backing field in the .NET compiled representation with the name `someField@`, and you access the stored value using a property named `someField`.</span></span>

<span data-ttu-id="dd701-128">Per un campo modificabile, la rappresentazione compilata .NET è un campo .NET.</span><span class="sxs-lookup"><span data-stu-id="dd701-128">For a mutable field, the .NET compiled representation is a .NET field.</span></span>


>[!WARNING] 
<span data-ttu-id="dd701-129">`Note`Lo spazio dei nomi .NET Framework `System.ComponentModel` contiene un attributo con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="dd701-129">`Note` The .NET Framework namespace `System.ComponentModel` contains an attribute that has the same name.</span></span> <span data-ttu-id="dd701-130">Per altre informazioni sull'attributo, vedere `System.ComponentModel.DefaultValueAttribute`.</span><span class="sxs-lookup"><span data-stu-id="dd701-130">For information about this attribute, see `System.ComponentModel.DefaultValueAttribute`.</span></span>


<span data-ttu-id="dd701-131">Nel codice seguente viene illustrato l'uso di campi espliciti e, per il confronto, un'associazione `let` in una classe che dispone di un costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="dd701-131">The following code shows the use of explicit fields and, for comparison, a `let` binding in a class that has a primary constructor.</span></span> <span data-ttu-id="dd701-132">Si noti che il campo associato `let` `myInt1` è privato.</span><span class="sxs-lookup"><span data-stu-id="dd701-132">Note that the `let`-bound field `myInt1` is private.</span></span> <span data-ttu-id="dd701-133">Quando si fa riferimento al campo associato `let` `myInt1` da un metodo membro, l'autoidentificatore `this` non è necessario.</span><span class="sxs-lookup"><span data-stu-id="dd701-133">When the `let`-bound field `myInt1` is referenced from a member method, the self identifier `this` is not required.</span></span> <span data-ttu-id="dd701-134">Ma quando si fa riferimento ai campi espliciti `myInt2` e `myString`, l'autoidentificatore è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd701-134">But when you are referencing the explicit fields `myInt2` and `myString`, the self identifier is required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

<span data-ttu-id="dd701-135">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dd701-135">The output is as follows:</span></span>

```
11 12 abc
30 def
```

<span data-ttu-id="dd701-136">Nel codice seguente viene illustrato come usare i campi espliciti in una classe che non dispone di un costruttore principale.</span><span class="sxs-lookup"><span data-stu-id="dd701-136">The following code shows the use of explicit fields in a class that does not have a primary constructor.</span></span> <span data-ttu-id="dd701-137">In questo caso, l'attributo `DefaultValue` non è obbligatorio, ma tutti i campi devono essere inizializzati nei costruttori definiti per il tipo.</span><span class="sxs-lookup"><span data-stu-id="dd701-137">In this case, the `DefaultValue` attribute is not required, but all the fields must be initialized in the constructors that are defined for the type.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

<span data-ttu-id="dd701-138">L'output è `35 22`.</span><span class="sxs-lookup"><span data-stu-id="dd701-138">The output is `35 22`.</span></span>

<span data-ttu-id="dd701-139">Nel codice seguente viene illustrato come usare i campi espliciti in una struttura.</span><span class="sxs-lookup"><span data-stu-id="dd701-139">The following code shows the use of explicit fields in a structure.</span></span> <span data-ttu-id="dd701-140">Poiché una struttura è un tipo di valore, dispone automaticamente di un costruttore predefinito che imposta i valori dei campi su zero.</span><span class="sxs-lookup"><span data-stu-id="dd701-140">Because a structure is a value type, it automatically has a default constructor that sets the values of its fields to zero.</span></span> <span data-ttu-id="dd701-141">Pertanto l'attributo `DefaultValue` non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dd701-141">Therefore, the `DefaultValue` attribute is not required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

<span data-ttu-id="dd701-142">L'output è `11 xyz`.</span><span class="sxs-lookup"><span data-stu-id="dd701-142">The output is `11 xyz`.</span></span>

<span data-ttu-id="dd701-143">I campi espliciti non sono destinati all'uso di routine.</span><span class="sxs-lookup"><span data-stu-id="dd701-143">Explicit fields are not intended for routine use.</span></span> <span data-ttu-id="dd701-144">In generale, quando possibile è consigliabile usare un'associazione `let` in una classe anziché un campo esplicito.</span><span class="sxs-lookup"><span data-stu-id="dd701-144">In general, when possible you should use a `let` binding in a class instead of an explicit field.</span></span> <span data-ttu-id="dd701-145">I campi espliciti sono utili in alcuni scenari di interoperabilità, ad esempio quando è necessario definire una struttura che verrà usata in una chiamata platform invoke per un'API nativa o in scenari di interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="dd701-145">Explicit fields are useful in certain interoperability scenarios, such as when you need to define a structure that will be used in a platform invoke call to a native API, or in COM interop scenarios.</span></span> <span data-ttu-id="dd701-146">Per ulteriori informazioni, vedere [funzioni esterne](../functions/external-functions.md).</span><span class="sxs-lookup"><span data-stu-id="dd701-146">For more information, see [External Functions](../functions/external-functions.md).</span></span> <span data-ttu-id="dd701-147">Un'altra situazione in cui un campo esplicito potrebbe essere necessario è quando si lavora con un generatore di codice F# che genera classi senza un costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="dd701-147">Another situation in which an explicit field might be necessary is when you are working with an F# code generator which emits classes without a primary constructor.</span></span> <span data-ttu-id="dd701-148">I campi espliciti sono utili anche per le variabili di thread statiche o per costrutti simili.</span><span class="sxs-lookup"><span data-stu-id="dd701-148">Explicit fields are also useful for thread-static variables or similar constructs.</span></span> <span data-ttu-id="dd701-149">Per altre informazioni, vedere `System.ThreadStaticAttribute`.</span><span class="sxs-lookup"><span data-stu-id="dd701-149">For more information, see `System.ThreadStaticAttribute`.</span></span>

<span data-ttu-id="dd701-150">Quando le parole chiave `member val` vengono visualizzate insieme in una definizione di tipo è una definizione di una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dd701-150">When the keywords `member val` appear together in a type definition, it is a definition of an automatically implemented property.</span></span> <span data-ttu-id="dd701-151">Per ulteriori informazioni, vedere [proprietà](properties.md).</span><span class="sxs-lookup"><span data-stu-id="dd701-151">For more information, see [Properties](properties.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="dd701-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd701-152">See Also</span></span>
[<span data-ttu-id="dd701-153">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dd701-153">Properties</span></span>](properties.md)

[<span data-ttu-id="dd701-154">Membri</span><span class="sxs-lookup"><span data-stu-id="dd701-154">Members</span></span>](index.md)

[<span data-ttu-id="dd701-155">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="dd701-155">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
