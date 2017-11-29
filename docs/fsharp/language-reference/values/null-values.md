---
title: Valori Null (F#)
description: 'Informazioni su come viene utilizzato il valore null in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 68ebd261-51cf-4582-b2dc-44c84d1c2500
ms.openlocfilehash: 01c14de00eb5efd0952145ffc8aabe69d65a3a48
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="null-values"></a><span data-ttu-id="600be-104">Valori Null</span><span class="sxs-lookup"><span data-stu-id="600be-104">Null Values</span></span>

<span data-ttu-id="600be-105">In questo argomento viene descritto come il valore null viene utilizzato in F #.</span><span class="sxs-lookup"><span data-stu-id="600be-105">This topic describes how the null value is used in F#.</span></span>


## <a name="null-value"></a><span data-ttu-id="600be-106">Valore null</span><span class="sxs-lookup"><span data-stu-id="600be-106">Null Value</span></span>
<span data-ttu-id="600be-107">Il valore null non viene utilizzato in genere in F # per variabili o valori.</span><span class="sxs-lookup"><span data-stu-id="600be-107">The null value is not normally used in F# for values or variables.</span></span> <span data-ttu-id="600be-108">Tuttavia, null come valore anomalo in determinate situazioni.</span><span class="sxs-lookup"><span data-stu-id="600be-108">However, null appears as an abnormal value in certain situations.</span></span> <span data-ttu-id="600be-109">Se un tipo è definito in F #, non è consentito null come valore normale, a meno che il [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attributo viene applicato al tipo.</span><span class="sxs-lookup"><span data-stu-id="600be-109">If a type is defined in F#, null is not permitted as a regular value unless the [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) attribute is applied to the type.</span></span> <span data-ttu-id="600be-110">Se un tipo è definito in un altro linguaggio .NET, null è un possibile valore, e quando si interagisce con tali tipi, il codice F # riscontrati valori null.</span><span class="sxs-lookup"><span data-stu-id="600be-110">If a type is defined in some other .NET language, null is a possible value, and when you are interoperating with such types, your F# code might encounter null values.</span></span>

<span data-ttu-id="600be-111">Per un tipo definito in F # e utilizzato esclusivamente da F #, l'unico modo per creare un valore null utilizzando direttamente la libreria F # consiste nell'utilizzare [unchecked. defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span><span class="sxs-lookup"><span data-stu-id="600be-111">For a type defined in F# and used strictly from F#, the only way to create a null value using the F# library directly is to use [Unchecked.defaultof](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) or [Array.zeroCreate](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2).</span></span> <span data-ttu-id="600be-112">Tuttavia, per un tipo di F # che viene usato da altri linguaggi .NET o se si utilizza tale tipo con un'API che non viene scritta in F #, ad esempio .NET Framework, possono verificarsi i valori null.</span><span class="sxs-lookup"><span data-stu-id="600be-112">However, for an F# type that is used from other .NET languages, or if you are using that type with an API that is not written in F#, such as the .NET Framework, null values can occur.</span></span>

<span data-ttu-id="600be-113">È possibile utilizzare il `option` tipo in F # quando è possibile utilizzare una variabile di riferimento con un valore null in un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="600be-113">You can use the `option` type in F# when you might use a reference variable with a possible null value in another .NET language.</span></span> <span data-ttu-id="600be-114">Invece di null, con F # `option` tipo, utilizzare il valore dell'opzione `None` se è presente alcun oggetto.</span><span class="sxs-lookup"><span data-stu-id="600be-114">Instead of null, with an F# `option` type, you use the option value `None` if there is no object.</span></span> <span data-ttu-id="600be-115">Utilizzare il valore dell'opzione `Some(obj)` con un oggetto `obj` quando è presente un oggetto.</span><span class="sxs-lookup"><span data-stu-id="600be-115">You use the option value `Some(obj)` with an object `obj` when there is an object.</span></span> <span data-ttu-id="600be-116">Per ulteriori informazioni, vedere [opzioni](../options.md).</span><span class="sxs-lookup"><span data-stu-id="600be-116">For more information, see [Options](../options.md).</span></span>

<span data-ttu-id="600be-117">Il `null` (parola chiave) è una parola chiave valida nel linguaggio F # ed è necessario utilizzarla quando si lavora con API di .NET Framework o altre API che vengono scritti in un altro linguaggio .NET.</span><span class="sxs-lookup"><span data-stu-id="600be-117">The `null` keyword is a valid keyword in the F# language, and you have to use it when you are working with .NET Framework APIs or other APIs that are written in another .NET language.</span></span> <span data-ttu-id="600be-118">Le due situazioni in cui potrebbe essere necessario un valore null sono quando si chiama un'API .NET e passa un valore null come argomento e quando si interpreta il valore restituito o parametro di output da una chiamata al metodo .NET.</span><span class="sxs-lookup"><span data-stu-id="600be-118">The two situations in which you might need a null value are when you call a .NET API and pass a null value as an argument, and when you interpret the return value or an output parameter from a .NET method call.</span></span>

<span data-ttu-id="600be-119">Per passare un valore null a un metodo .NET, usare semplicemente il `null` (parola chiave) nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="600be-119">To pass a null value to a .NET method, just use the `null` keyword in the calling code.</span></span> <span data-ttu-id="600be-120">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="600be-120">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

<span data-ttu-id="600be-121">Per interpretare un valore null viene ottenuto da un metodo .NET, usare criteri di ricerca se possibile.</span><span class="sxs-lookup"><span data-stu-id="600be-121">To interpret a null value that is obtained from a .NET method, use pattern matching if you can.</span></span> <span data-ttu-id="600be-122">Esempio di codice seguente viene illustrato come utilizzare criteri di ricerca per interpretare il valore null restituito da `ReadLine` quando tenta di leggere oltre la fine di un flusso di input.</span><span class="sxs-lookup"><span data-stu-id="600be-122">The following code example shows how to use pattern matching to interpret the null value that is returned from `ReadLine` when it tries to read past the end of an input stream.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

<span data-ttu-id="600be-123">Valori null per i tipi F # possono essere generati anche in altri modi, ad esempio quando si usa `Array.zeroCreate`, che chiama `Unchecked.defaultof`.</span><span class="sxs-lookup"><span data-stu-id="600be-123">Null values for F# types can also be generated in other ways, such as when you use `Array.zeroCreate`, which calls `Unchecked.defaultof`.</span></span> <span data-ttu-id="600be-124">È necessario prestare attenzione con tale codice per mantenere i valori null incapsulati.</span><span class="sxs-lookup"><span data-stu-id="600be-124">You must be careful with such code to keep the null values encapsulated.</span></span> <span data-ttu-id="600be-125">In una libreria destinata solo a F #, non è necessario verificare la presenza di valori null in ogni funzione.</span><span class="sxs-lookup"><span data-stu-id="600be-125">In a library intended only for F#, you do not have to check for null values in every function.</span></span> <span data-ttu-id="600be-126">Se si scrive una raccolta per l'interoperabilità con altri linguaggi .NET, potrebbe essere necessario aggiungere i controlli per i valori null, i parametri di input e generano un `ArgumentNullException`, esattamente come avviene nel codice c# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="600be-126">If you are writing a library for interoperation with other .NET languages, you might have to add checks for null input parameters and throw an `ArgumentNullException`, just as you do in C# or Visual Basic code.</span></span>

<span data-ttu-id="600be-127">È possibile utilizzare il codice seguente per verificare se un valore arbitrario è null.</span><span class="sxs-lookup"><span data-stu-id="600be-127">You can use the following code to check if an arbitrary value is null.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a><span data-ttu-id="600be-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="600be-128">See Also</span></span>
[<span data-ttu-id="600be-129">Valori</span><span class="sxs-lookup"><span data-stu-id="600be-129">Values</span></span>](index.md)

[<span data-ttu-id="600be-130">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="600be-130">Match Expressions</span></span>](../match-expressions.md)
