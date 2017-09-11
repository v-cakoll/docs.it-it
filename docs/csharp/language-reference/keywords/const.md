---
title: const (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 28
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
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a><span data-ttu-id="986b5-102">const (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="986b5-102">const (C# Reference)</span></span>
<span data-ttu-id="986b5-103">Si usa la parola chiave `const` per dichiarare un campo costante o una variabile locale costante.</span><span class="sxs-lookup"><span data-stu-id="986b5-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="986b5-104">I campi e le variabili locali costanti non sono variabili e non sono quindi modificabili.</span><span class="sxs-lookup"><span data-stu-id="986b5-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="986b5-105">Gli elementi costanti possono essere numeri, valori booleani, stringhe o un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="986b5-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="986b5-106">Non creare una costante per rappresentare informazioni di cui si prevede la modifica in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="986b5-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="986b5-107">Un campo costante, ad esempio, non deve essere usato per archiviare il prezzo di un servizio, il numero di versione di un prodotto o il nome dell'organizzazione di una società.</span><span class="sxs-lookup"><span data-stu-id="986b5-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="986b5-108">Tali valori potrebbero cambiare nel tempo e, poiché i compilatori propagano le costanti, eventuale altro codice compilato con quelle librerie dovrebbe essere ricompilato per riflettere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="986b5-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="986b5-109">Vedere anche la parola chiave [readonly](../../../csharp/language-reference/keywords/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="986b5-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="986b5-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="986b5-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="986b5-111">Note</span><span class="sxs-lookup"><span data-stu-id="986b5-111">Remarks</span></span>  
 <span data-ttu-id="986b5-112">Il tipo di una dichiarazione di costante specifica il tipo di membri introdotti dalla dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="986b5-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="986b5-113">L'inizializzatore di una variabile locale costante o di un campo costante deve essere un'espressione costante che possa essere convertita in modo implicito nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="986b5-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="986b5-114">Un'espressione di costanti è un'espressione che può essere valutata interamente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="986b5-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="986b5-115">Di conseguenza, gli unici valori possibili per le costanti dei tipi di riferimento sono `string` e il riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="986b5-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="986b5-116">La dichiarazione di costante può includere più costanti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="986b5-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="986b5-117">Il modificatore `static` non è consentito in una dichiarazione di costante.</span><span class="sxs-lookup"><span data-stu-id="986b5-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="986b5-118">Una costante può far parte di un'espressione costante, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="986b5-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="986b5-119">La parola chiave [readonly](../../../csharp/language-reference/keywords/readonly.md) è diversa dalla parola chiave `const`.</span><span class="sxs-lookup"><span data-stu-id="986b5-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="986b5-120">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="986b5-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="986b5-121">Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="986b5-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="986b5-122">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="986b5-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="986b5-123">Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nella riga seguente: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="986b5-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="986b5-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="986b5-124">Example</span></span>  
 <span data-ttu-id="986b5-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="986b5-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="986b5-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="986b5-126">Example</span></span>  
 <span data-ttu-id="986b5-127">In questo esempio viene illustrato come usare le costanti come variabili locali.</span><span class="sxs-lookup"><span data-stu-id="986b5-127">This example demonstrates how to use constants as local variables.</span></span>  
  
 <span data-ttu-id="986b5-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="986b5-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="986b5-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="986b5-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="986b5-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="986b5-130">See Also</span></span>  
 <span data-ttu-id="986b5-131">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="986b5-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="986b5-132">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="986b5-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="986b5-133">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="986b5-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="986b5-134">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="986b5-134">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="986b5-135">readonly</span><span class="sxs-lookup"><span data-stu-id="986b5-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

