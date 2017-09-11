---
title: dynamic (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
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
ms.openlocfilehash: b68a6ef4dc3dda01638b9bb84db58ba77214f490
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="dynamic-c-reference"></a><span data-ttu-id="175e0-102">dynamic (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="175e0-102">dynamic (C# Reference)</span></span>
<span data-ttu-id="175e0-103">`dynamic` abilita le operazioni in cui il tipo appare per ignorare il controllo del tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="175e0-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="175e0-104">Queste operazioni vengono risolte in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="175e0-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="175e0-105">Il tipo `dynamic` semplifica l'accesso alle API COM, ad esempio le API di automazione di Office, e anche ad API dinamiche come le librerie di IronPython e al modello DOM (Document Object Model) HTML.</span><span class="sxs-lookup"><span data-stu-id="175e0-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="175e0-106">Il tipo `dynamic` si comporta come tipo `object` nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="175e0-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="175e0-107">Tuttavia, le operazioni che contengono espressioni di tipo `dynamic` non vengono risolte o il tipo non viene verificato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="175e0-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="175e0-108">Il compilatore raggruppa le informazioni sull'operazione e tali informazioni successivamente vengono usate per valutare l'operazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="175e0-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="175e0-109">Come parte del processo, le variabili di tipo `dynamic` vengono compilate in variabili di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="175e0-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="175e0-110">Di conseguenza, il tipo `dynamic` esiste solo in fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="175e0-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>  
  
 <span data-ttu-id="175e0-111">Nell'esempio seguente vengono messe a confronto una variabile di tipo `dynamic` e una variabile di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="175e0-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="175e0-112">Per verificare il tipo di ogni variabile in fase di compilazione, posizionare il puntatore del mouse su `dyn` o `obj` nelle istruzioni `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="175e0-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="175e0-113">IntelliSense visualizza **dynamic** per `dyn` e **object** per `obj`.</span><span class="sxs-lookup"><span data-stu-id="175e0-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>  
  
 <span data-ttu-id="175e0-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="175e0-114">[!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]</span></span>  
  
 <span data-ttu-id="175e0-115">Le istruzioni `WriteLine` visualizzano i tipi in fase di esecuzione di `dyn` e `obj`.</span><span class="sxs-lookup"><span data-stu-id="175e0-115">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="175e0-116">A questo punto, entrambe hanno lo stesso tipo, un numero intero.</span><span class="sxs-lookup"><span data-stu-id="175e0-116">At that point, both have the same type, integer.</span></span> <span data-ttu-id="175e0-117">Viene generato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="175e0-117">The following output is produced:</span></span>  
  
 `System.Int32`  
  
 `System.Int32`  
  
 <span data-ttu-id="175e0-118">Per vedere la differenza tra `dyn` e `obj` in fase di compilazione, aggiungere le due righe seguenti tra le dichiarazioni e le istruzioni `WriteLine` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="175e0-118">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 <span data-ttu-id="175e0-119">Viene segnalato un errore del compilatore per il tentativo di aggiunta di un numero intero e di un oggetto nell'espressione `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="175e0-119">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="175e0-120">Tuttavia non vengono segnalati errori per `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="175e0-120">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="175e0-121">L'espressione che contiene `dyn` non viene controllata in fase di compilazione perché il tipo di `dyn` è `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="175e0-121">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>  
  
## <a name="context"></a><span data-ttu-id="175e0-122">Contesto</span><span class="sxs-lookup"><span data-stu-id="175e0-122">Context</span></span>  
 <span data-ttu-id="175e0-123">La parola chiave `dynamic` può apparire direttamente o come componente di un tipo costruito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="175e0-123">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>  
  
-   <span data-ttu-id="175e0-124">Nelle dichiarazioni, come tipo di proprietà, campo, indicizzatore, parametro, valore restituito, variabile locale o vincolo di tipo.</span><span class="sxs-lookup"><span data-stu-id="175e0-124">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="175e0-125">La definizione di classe seguente usa `dynamic` in molte dichiarazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="175e0-125">The following class definition uses `dynamic` in several different declarations.</span></span>  
  
     <span data-ttu-id="175e0-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="175e0-126">[!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]</span></span>  
  
-   <span data-ttu-id="175e0-127">Nelle conversioni di tipo esplicito, ad esempio il tipo di destinazione di una conversione.</span><span class="sxs-lookup"><span data-stu-id="175e0-127">In explicit type conversions, as the target type of a conversion.</span></span>  
  
     <span data-ttu-id="175e0-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="175e0-128">[!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]</span></span>  
  
-   <span data-ttu-id="175e0-129">In qualsiasi contesto in cui i tipi vengono usati come valori, ad esempio sul lato destro di un operatore `is` o un operatore `as`, o come argomento di `typeof` come parte di un tipo costruito.</span><span class="sxs-lookup"><span data-stu-id="175e0-129">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="175e0-130">Ad esempio, `dynamic` può essere usato nelle espressioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="175e0-130">For example, `dynamic` can be used in the following expressions.</span></span>  
  
     <span data-ttu-id="175e0-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="175e0-131">[!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="175e0-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="175e0-132">Example</span></span>  
 <span data-ttu-id="175e0-133">Nell'esempio seguente viene usato `dynamic` in diverse dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="175e0-133">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="175e0-134">Il metodo `Main` confronta anche il controllo dei tipi in fase di compilazione con il controllo dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="175e0-134">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>  
  
 <span data-ttu-id="175e0-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="175e0-135">[!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]</span></span>  
  
 <span data-ttu-id="175e0-136">Per altre informazioni ed esempi, vedere [Uso del tipo dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="175e0-136">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175e0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="175e0-137">See Also</span></span>  
 <span data-ttu-id="175e0-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="175e0-138"><xref:System.Dynamic.ExpandoObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="175e0-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="175e0-139"><xref:System.Dynamic.DynamicObject?displayProperty=fullName></span></span>   
 <span data-ttu-id="175e0-140">[Uso del tipo dinamico](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-140">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="175e0-141">[object](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-141">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="175e0-142">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-142">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="175e0-143">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-143">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 <span data-ttu-id="175e0-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-144">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="175e0-145">[Procedura: Eseguire il cast sicuro usando gli operatori as e is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span><span class="sxs-lookup"><span data-stu-id="175e0-145">[How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md) </span></span>  
 [<span data-ttu-id="175e0-146">Procedura dettagliata: Creazione e utilizzo di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="175e0-146">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)

