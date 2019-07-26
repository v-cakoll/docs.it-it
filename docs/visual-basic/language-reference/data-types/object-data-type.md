---
title: Tipo di dati Object (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513054"
---
# <a name="object-data-type"></a><span data-ttu-id="c5999-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="c5999-102">Object Data Type</span></span>

<span data-ttu-id="c5999-103">Include indirizzi che fanno riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="c5999-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="c5999-104">È possibile assegnare qualsiasi tipo di riferimento (stringa, matrice, classe o interfaccia) a una `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="c5999-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="c5999-105">Una `Object` variabile può anche fare riferimento a dati di qualsiasi tipo di valore ( `Boolean`numeric `Char`, `Date`,,, Structure o Enumeration).</span><span class="sxs-lookup"><span data-stu-id="c5999-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="c5999-106">Note</span><span class="sxs-lookup"><span data-stu-id="c5999-106">Remarks</span></span>

<span data-ttu-id="c5999-107">Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, inclusa qualsiasi istanza di oggetto riconosciuta dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5999-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="c5999-108">Usare `Object` quando non si conosce in fase di compilazione a quale tipo di dati può puntare la variabile.</span><span class="sxs-lookup"><span data-stu-id="c5999-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="c5999-109">Il valore predefinito di `Object` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="c5999-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="c5999-110">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c5999-110">Data Types</span></span>

<span data-ttu-id="c5999-111">È possibile assegnare una variabile, una costante o un'espressione di qualsiasi tipo di dati `Object` a una variabile.</span><span class="sxs-lookup"><span data-stu-id="c5999-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="c5999-112">Per determinare il tipo di dati `Object` a cui fa attualmente riferimento una variabile, è <xref:System.Type.GetTypeCode%2A> possibile usare il <xref:System.Type?displayProperty=nameWithType> metodo della classe.</span><span class="sxs-lookup"><span data-stu-id="c5999-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c5999-113">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c5999-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="c5999-114">Il `Object` tipo di dati è un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c5999-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="c5999-115">Tuttavia, Visual Basic considera una `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="c5999-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="c5999-116">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="c5999-116">Storage</span></span>

<span data-ttu-id="c5999-117">Indipendentemente dal tipo di dati a cui `Object` fa riferimento, una variabile non contiene il valore di dati stesso, bensì un puntatore al valore.</span><span class="sxs-lookup"><span data-stu-id="c5999-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="c5999-118">Usa sempre quattro byte nella memoria del computer, ma non include l'archiviazione per i dati che rappresentano il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="c5999-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="c5999-119">A causa del codice che usa il puntatore per individuare i dati, `Object` le variabili che mantengono i tipi di valore sono leggermente più lente per accedere alle variabili tipizzate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="c5999-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="c5999-120">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="c5999-120">Programming Tips</span></span>

- <span data-ttu-id="c5999-121">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="c5999-121">**Interop Considerations.**</span></span> <span data-ttu-id="c5999-122">Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti com o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con il `Object` tipo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c5999-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="c5999-123">**Prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="c5999-123">**Performance.**</span></span> <span data-ttu-id="c5999-124">Una variabile dichiarata con `Object` il tipo è sufficientemente flessibile da contenere un riferimento a qualsiasi oggetto.</span><span class="sxs-lookup"><span data-stu-id="c5999-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="c5999-125">Tuttavia, quando si richiama un metodo o una proprietà in una variabile di questo tipo, si verifica sempre un' *associazione tardiva* (in fase di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="c5999-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="c5999-126">Per forzare l' *associazione anticipata* (in fase di compilazione) e migliorare le prestazioni, dichiarare la variabile con un nome di classe specifico oppure eseguirne il cast al tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="c5999-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="c5999-127">Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifico, ad <xref:System.OperatingSystem>esempio, anziché il `Object` tipo generalizzato.</span><span class="sxs-lookup"><span data-stu-id="c5999-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="c5999-128">È inoltre consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control>anziché, in modo da poter accedere alle proprietà e ai metodi.</span><span class="sxs-lookup"><span data-stu-id="c5999-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="c5999-129">In genere, è possibile usare l'elenco delle **classi** nella **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.</span><span class="sxs-lookup"><span data-stu-id="c5999-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="c5999-130">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="c5999-130">**Widening.**</span></span> <span data-ttu-id="c5999-131">Tutti i tipi di dati e tutti i tipi di `Object` riferimento vengono ampliati al tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c5999-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="c5999-132">Ciò significa che è possibile convertire qualsiasi tipo `Object` in senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="c5999-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="c5999-133">Tuttavia, se si esegue la conversione tra tipi `Object`di valore e, Visual Basic esegue operazioni denominate *Boxing* *e unboxing*, che rendono l'esecuzione più lenta.</span><span class="sxs-lookup"><span data-stu-id="c5999-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="c5999-134">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="c5999-134">**Type Characters.**</span></span> <span data-ttu-id="c5999-135">`Object`non ha un carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="c5999-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="c5999-136">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="c5999-136">**Framework Type.**</span></span> <span data-ttu-id="c5999-137">Il tipo corrispondente nella .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="c5999-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="c5999-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5999-138">Example</span></span>

<span data-ttu-id="c5999-139">Nell'esempio seguente viene illustrata `Object` una variabile che punta a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c5999-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="c5999-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5999-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="c5999-141">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c5999-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="c5999-142">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="c5999-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c5999-143">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="c5999-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="c5999-144">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="c5999-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="c5999-145">Procedura: Determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="c5999-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="c5999-146">Procedura: Determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="c5999-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
