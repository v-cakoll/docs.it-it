---
title: Tipo di dati di oggetto (Visual Basic)
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
ms.openlocfilehash: 94d3ddcf71194eb69a2d26bcdf549aaf693e46e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485560"
---
# <a name="object-data-type"></a><span data-ttu-id="1f2f2-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="1f2f2-102">Object Data Type</span></span>
<span data-ttu-id="1f2f2-103">Contiene gli indirizzi che fanno riferimento a oggetti.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="1f2f2-104">È possibile assegnare qualsiasi tipo riferimento (stringa, matrice, classe o interfaccia) a un `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="1f2f2-105">Un' `Object` variabile anche possibile fare riferimento ai dati di qualsiasi tipo di valore (numerico `Boolean`, `Char`, `Date`, struttura o enumerazione).</span><span class="sxs-lookup"><span data-stu-id="1f2f2-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f2f2-106">Note</span><span class="sxs-lookup"><span data-stu-id="1f2f2-106">Remarks</span></span>  
 <span data-ttu-id="1f2f2-107">Il `Object` tipo di dati può puntare a dati di qualsiasi tipo di dati, tra cui le istanze di oggetto riconosciuto dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="1f2f2-108">Usare `Object` quando non si conosce in fase di compilazione la variabile di tipo i dati che potrebbe fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="1f2f2-109">Il valore predefinito `Object` è `Nothing` (un riferimento null).</span><span class="sxs-lookup"><span data-stu-id="1f2f2-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="1f2f2-110">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1f2f2-110">Data Types</span></span>  
 <span data-ttu-id="1f2f2-111">È possibile assegnare una variabile, costante o espressione di qualsiasi tipo di dati per un `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="1f2f2-112">Per determinare il tipo di dati un `Object` attualmente fa riferimento alla variabile, è possibile usare il <xref:System.Type.GetTypeCode%2A> metodo il <xref:System.Type?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="1f2f2-113">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="1f2f2-114">Il `Object` tipo di dati è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="1f2f2-115">Tuttavia, Visual Basic considera un `Object` variabile come tipo di valore quando fa riferimento ai dati di un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="1f2f2-116">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="1f2f2-116">Storage</span></span>  
 <span data-ttu-id="1f2f2-117">Qualsiasi tipo di dati fa riferimento, un `Object` variabile non contiene il valore di dati stesso, ma piuttosto un puntatore al valore.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="1f2f2-118">Usare sempre i quattro byte nella memoria del computer, ma questo non include lo spazio di archiviazione per i dati che rappresenta il valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="1f2f2-119">A causa del codice che utilizza il puntatore del mouse per individuare i dati, `Object` variabili che contengono i tipi di valore sono leggermente più lente accedere in modo esplicito rispetto alle variabili di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="1f2f2-120">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="1f2f2-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="1f2f2-121">**Considerazioni sull'interoperabilità.**</span><span class="sxs-lookup"><span data-stu-id="1f2f2-121">**Interop Considerations.**</span></span> <span data-ttu-id="1f2f2-122">Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di puntatore in altri ambienti non sono compatibili con Visual Basic `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="1f2f2-123">**Prestazioni.**</span><span class="sxs-lookup"><span data-stu-id="1f2f2-123">**Performance.**</span></span> <span data-ttu-id="1f2f2-124">Una variabile dichiarata con la `Object` è sufficientemente flessibile per contenere un riferimento a qualsiasi oggetto di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="1f2f2-125">Tuttavia, quando si richiama un metodo o una proprietà su tale variabile, si verifica sempre *associazione tardiva* (in fase di esecuzione).</span><span class="sxs-lookup"><span data-stu-id="1f2f2-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="1f2f2-126">Per forzare *associazione anticipata* (in fase di compilazione) e ottenere prestazioni migliori, dichiarare la variabile con un nome di classe specifici o eseguirne il cast al tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="1f2f2-127">Quando si dichiara una variabile oggetto, provare a usare un tipo di classe specifica, ad esempio <xref:System.OperatingSystem>, anziché il generalizzato `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="1f2f2-128">È anche consigliabile utilizzare la classe più specifica disponibile, ad esempio <xref:System.Windows.Forms.TextBox> invece di <xref:System.Windows.Forms.Control>, in modo che è possibile accedere ai relativi metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="1f2f2-129">In genere, è possibile usare la **classi** nell'elenco il **Visualizzatore oggetti** per trovare i nomi delle classi disponibili.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="1f2f2-130">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="1f2f2-130">**Widening.**</span></span> <span data-ttu-id="1f2f2-131">Tutti i tipi di dati e tutti i tipi riferimento ampliano il `Object` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="1f2f2-132">Ciò significa che è possibile convertire qualsiasi tipo a `Object` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="1f2f2-133">Tuttavia, se è la conversione tra tipi di valore e `Object`, Visual Basic esegue operazioni chiamate *boxing* e *unboxing*, quale verificare l'esecuzione più lenta.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="1f2f2-134">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="1f2f2-134">**Type Characters.**</span></span> <span data-ttu-id="1f2f2-135">`Object` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="1f2f2-136">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="1f2f2-136">**Framework Type.**</span></span> <span data-ttu-id="1f2f2-137">Il tipo corrispondente in .NET Framework è la <xref:System.Object?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f2f2-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f2f2-138">Example</span></span>  
 <span data-ttu-id="1f2f2-139">L'esempio seguente illustra un `Object` variabile sta puntando a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1f2f2-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f2f2-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f2f2-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="1f2f2-141">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1f2f2-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="1f2f2-142">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="1f2f2-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1f2f2-143">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="1f2f2-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="1f2f2-144">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="1f2f2-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="1f2f2-145">Procedura: determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="1f2f2-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="1f2f2-146">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="1f2f2-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
