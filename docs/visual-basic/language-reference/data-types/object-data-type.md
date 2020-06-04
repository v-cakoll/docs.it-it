---
title: Object Data Type
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
ms.openlocfilehash: 14770e74a0169dba3a45a04845dd32323e6201e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415583"
---
# <a name="object-data-type"></a><span data-ttu-id="a4c0e-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="a4c0e-102">Object Data Type</span></span>

<span data-ttu-id="a4c0e-103">Include indirizzi che fanno riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="a4c0e-104">È possibile assegnare qualsiasi tipo di riferimento (stringa, matrice, classe o interfaccia) a una `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="a4c0e-105">Una `Object` variabile può anche fare riferimento a dati di qualsiasi tipo di valore (numeric,,,, `Boolean` `Char` `Date` Structure o Enumeration).</span><span class="sxs-lookup"><span data-stu-id="a4c0e-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="a4c0e-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="a4c0e-106">Remarks</span></span>

<span data-ttu-id="a4c0e-107">Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, inclusa qualsiasi istanza di oggetto riconosciuta dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="a4c0e-108">Usare `Object` quando non si conosce in fase di compilazione a quale tipo di dati può puntare la variabile.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="a4c0e-109">Il valore predefinito di `Object` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="a4c0e-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="a4c0e-110">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a4c0e-110">Data Types</span></span>

<span data-ttu-id="a4c0e-111">È possibile assegnare una variabile, una costante o un'espressione di qualsiasi tipo di dati a una `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="a4c0e-112">Per determinare il tipo di dati `Object` a cui fa attualmente riferimento una variabile, è possibile usare il <xref:System.Type.GetTypeCode%2A> metodo della <xref:System.Type?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a4c0e-113">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="a4c0e-114">Il `Object` tipo di dati è un tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="a4c0e-115">Tuttavia, Visual Basic considera una `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="a4c0e-116">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="a4c0e-116">Storage</span></span>

<span data-ttu-id="a4c0e-117">Indipendentemente dal tipo di dati a cui fa riferimento, una `Object` variabile non contiene il valore di dati stesso, bensì un puntatore al valore.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="a4c0e-118">Usa sempre quattro byte nella memoria del computer, ma non include l'archiviazione per i dati che rappresentano il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="a4c0e-119">A causa del codice che usa il puntatore per individuare i dati, le `Object` variabili che mantengono i tipi di valore sono leggermente più lente per accedere alle variabili tipizzate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="a4c0e-120">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="a4c0e-120">Programming Tips</span></span>

- <span data-ttu-id="a4c0e-121">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="a4c0e-121">**Interop Considerations.**</span></span> <span data-ttu-id="a4c0e-122">Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con il `Object` tipo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="a4c0e-123">**Prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="a4c0e-123">**Performance.**</span></span> <span data-ttu-id="a4c0e-124">Una variabile dichiarata con il `Object` tipo è sufficientemente flessibile da contenere un riferimento a qualsiasi oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="a4c0e-125">Tuttavia, quando si richiama un metodo o una proprietà in una variabile di questo tipo, si verifica sempre un' *associazione tardiva* (in fase di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="a4c0e-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="a4c0e-126">Per forzare l' *associazione anticipata* (in fase di compilazione) e migliorare le prestazioni, dichiarare la variabile con un nome di classe specifico oppure eseguirne il cast al tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="a4c0e-127">Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifico, ad esempio <xref:System.OperatingSystem> , anziché il tipo generalizzato `Object` .</span><span class="sxs-lookup"><span data-stu-id="a4c0e-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="a4c0e-128">È inoltre consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> anziché <xref:System.Windows.Forms.Control> , in modo da poter accedere alle proprietà e ai metodi.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="a4c0e-129">In genere, è possibile usare l'elenco delle **classi** nella **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="a4c0e-130">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="a4c0e-130">**Widening.**</span></span> <span data-ttu-id="a4c0e-131">Tutti i tipi di dati e tutti i tipi di riferimento vengono ampliati al `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="a4c0e-132">Ciò significa che è possibile convertire qualsiasi tipo in `Object` senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="a4c0e-133">Tuttavia, se si esegue la conversione tra tipi di valore e `Object` , Visual Basic esegue operazioni *unboxing*denominate *Boxing* e unboxing, che rendono l'esecuzione più lenta.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="a4c0e-134">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="a4c0e-134">**Type Characters.**</span></span> <span data-ttu-id="a4c0e-135">`Object`non ha un carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="a4c0e-136">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="a4c0e-136">**Framework Type.**</span></span> <span data-ttu-id="a4c0e-137">Il tipo corrispondente nella .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="a4c0e-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4c0e-138">Example</span></span>

<span data-ttu-id="a4c0e-139">Nell'esempio seguente viene illustrata una `Object` variabile che punta a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a4c0e-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="a4c0e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4c0e-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="a4c0e-141">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a4c0e-141">Data Types</span></span>](index.md)
- [<span data-ttu-id="a4c0e-142">CString</span><span class="sxs-lookup"><span data-stu-id="a4c0e-142">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="a4c0e-143">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="a4c0e-143">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="a4c0e-144">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a4c0e-144">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="a4c0e-145">Procedura: determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="a4c0e-145">How to: Determine Whether Two Objects Are Related</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="a4c0e-146">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="a4c0e-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
