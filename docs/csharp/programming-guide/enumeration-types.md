---
title: Tipi di enumerazione (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
caps.latest.revision: 17
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
ms.openlocfilehash: 677de7c6e0c0f72b600ce8ee5a8bad265725f6d3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="enumeration-types-c-programming-guide"></a><span data-ttu-id="65125-102">Tipi di enumerazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="65125-102">Enumeration Types (C# Programming Guide)</span></span>
<span data-ttu-id="65125-103">Un tipo di enumerazione (detto anche enumerazione o enum) rappresenta un modo efficiente per definire un set di costanti integrali denominate che possono essere assegnate a una variabile.</span><span class="sxs-lookup"><span data-stu-id="65125-103">An enumeration type (also named an enumeration or an enum) provides an efficient way to define a set of named integral constants that may be assigned to a variable.</span></span> <span data-ttu-id="65125-104">Si supponga ad esempio di dover definire una variabile il cui valore rappresenterà un giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="65125-104">For example, assume that you have to define a variable whose value will represent a day of the week.</span></span> <span data-ttu-id="65125-105">Ci sono solo sette valori significativi che la variabile potrà mai archiviare.</span><span class="sxs-lookup"><span data-stu-id="65125-105">There are only seven meaningful values which that variable will ever store.</span></span> <span data-ttu-id="65125-106">Per definire tali valori, è possibile usare un tipo di enumerazione, dichiarato tramite la parola chiave [enum](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="65125-106">To define those values, you can use an enumeration type, which is declared by using the [enum](../../csharp/language-reference/keywords/enum.md) keyword.</span></span>  
  
 <span data-ttu-id="65125-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-107">[!code-cs[csProgGuideEnums#1](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_1.cs)]</span></span>  
  
 <span data-ttu-id="65125-108">Per impostazione predefinita, il tipo sottostante di ogni elemento dell'enumerazione è [int](../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="65125-108">By default the underlying type of each element in the enum is [int](../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="65125-109">È possibile specificare un altro tipo numerico integrale usando i due punti, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="65125-109">You can specify another integral numeric type by using a colon, as shown in the previous example.</span></span> <span data-ttu-id="65125-110">Per un elenco completo dei tipi possibili, vedere [enum (Riferimenti per C#)](../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="65125-110">For a full list of possible types, see [enum (C# Reference)](../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="65125-111">È possibile verificare i valori numerici sottostanti eseguendo il cast al tipo sottostante, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="65125-111">You can verify the underlying numeric values by casting  to the underlying type, as the following example shows.</span></span>  
  
```csharp  
Days today = Days.Monday;  
int dayNumber =(int)today;  
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);  
  
Months thisMonth = Months.Dec;  
byte monthNumber = (byte)thisMonth;  
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);  
  
// Output:  
// Monday is day number #1.  
// Dec is month number #11.  
```  
  
 <span data-ttu-id="65125-112">I vantaggi dell'uso di enum anziché di un tipo numerico sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="65125-112">The following are advantages of using an enum instead of a numeric type:</span></span>  
  
-   <span data-ttu-id="65125-113">Si specifica in modo chiaro per il codice client quali sono i valori validi per la variabile.</span><span class="sxs-lookup"><span data-stu-id="65125-113">You clearly specify for client code which values are valid for the variable.</span></span>  
  
-   <span data-ttu-id="65125-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense elenca i valori definiti.</span><span class="sxs-lookup"><span data-stu-id="65125-114">In [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], IntelliSense lists the defined values.</span></span>  
  
 <span data-ttu-id="65125-115">Quando non si specificano valori per gli elementi nell'elenco di enumeratori, i valori vengono incrementati automaticamente di 1.</span><span class="sxs-lookup"><span data-stu-id="65125-115">When you do not specify values for the elements in the enumerator list, the values are automatically incremented by 1.</span></span> <span data-ttu-id="65125-116">Nell'esempio precedente, `Days.Sunday` ha valore 0, `Days.Monday` ha valore 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="65125-116">In the previous example, `Days.Sunday` has a value of 0, `Days.Monday` has a value of 1, and so on.</span></span> <span data-ttu-id="65125-117">Quando si crea un nuovo oggetto `Days`, se a questo non si assegna un valore in modo esplicito, l'oggetto avrà il valore predefinito `Days.Sunday` (0).</span><span class="sxs-lookup"><span data-stu-id="65125-117">When you create a new `Days` object, it will have a default value of `Days.Sunday` (0) if you do not explicitly assign it a value.</span></span> <span data-ttu-id="65125-118">Quando si crea un enum, selezionare il valore predefinito più logico e assegnare a questo un valore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="65125-118">When you create an enum, select the most logical default value and give it a value of zero.</span></span> <span data-ttu-id="65125-119">In tal modo tutti gli enum avranno quel valore predefinito, se non è stato loro assegnato un valore in modo esplicito al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="65125-119">That will cause all enums to have that default value if they are not explicitly assigned a value when they are created.</span></span>  
  
 <span data-ttu-id="65125-120">Se la variabile `meetingDay` è di tipo `Days`, è possibile assegnare (senza un cast esplicito) solo uno dei valori definiti da `Days`.</span><span class="sxs-lookup"><span data-stu-id="65125-120">If the variable `meetingDay` is of type `Days`, then (without an explicit cast) you can only assign it one of the values defined by `Days`.</span></span> <span data-ttu-id="65125-121">E se il giorno della riunione cambia, è possibile assegnare un nuovo valore da `Days` a `meetingDay`:</span><span class="sxs-lookup"><span data-stu-id="65125-121">And if the meeting day changes, you can assign a new value from `Days` to `meetingDay`:</span></span>  
  
 <span data-ttu-id="65125-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-122">[!code-cs[csProgGuideEnums#4](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65125-123">È possibile assegnare a `meetingDay` qualsiasi valore intero arbitrario.</span><span class="sxs-lookup"><span data-stu-id="65125-123">It is possible to assign any arbitrary integer value to `meetingDay`.</span></span> <span data-ttu-id="65125-124">Ad esempio, questa riga di codice non genera un errore: `meetingDay = (Days) 42`.</span><span class="sxs-lookup"><span data-stu-id="65125-124">For example, this line of code does not produce an error: `meetingDay = (Days) 42`.</span></span> <span data-ttu-id="65125-125">Questa impostazione, tuttavia, non è consigliabile perché l'aspettativa implicita è che una variabile enum contenga solo uno dei valori definiti dal tipo enum.</span><span class="sxs-lookup"><span data-stu-id="65125-125">However, you should not do this because the implicit expectation is that an enum variable will only hold one of the values defined by the enum.</span></span> <span data-ttu-id="65125-126">L'assegnazione di un valore arbitrario a una variabile di tipo enum comporta un rischio elevato di errore.</span><span class="sxs-lookup"><span data-stu-id="65125-126">To assign an arbitrary value to a variable of an enumeration type is to introduce a high risk for errors.</span></span>  
  
 <span data-ttu-id="65125-127">È possibile assegnare qualsiasi valore agli elementi nell'elenco di enumeratori di un tipo di enumerazione ed è anche possibile usare valori calcolati:</span><span class="sxs-lookup"><span data-stu-id="65125-127">You can assign any values to the elements in the enumerator list of an enumeration type, and you can also use computed values:</span></span>  
  
 <span data-ttu-id="65125-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-128">[!code-cs[csProgGuideEnums#3](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_3.cs)]</span></span>  
  
## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="65125-129">Tipi di enumerazione come flag di bit</span><span class="sxs-lookup"><span data-stu-id="65125-129">Enumeration Types as Bit Flags</span></span>  
 <span data-ttu-id="65125-130">È possibile usare un tipo di enumerazione per definire flag di bit, che consentono a un'istanza del tipo di enumerazione di archiviare qualsiasi combinazione dei valori definiti nell'elenco di enumeratori.</span><span class="sxs-lookup"><span data-stu-id="65125-130">You can use an enumeration type to define bit flags, which enables an instance of the enumeration type to store any combination of the values that are defined in the enumerator list.</span></span> <span data-ttu-id="65125-131">Naturalmente alcune combinazioni potrebbero non essere significative o consentite nel codice del programma.</span><span class="sxs-lookup"><span data-stu-id="65125-131">(Of course, some combinations may not be meaningful or allowed in your program code.)</span></span>  
  
 <span data-ttu-id="65125-132">Un enum di flag di bit viene creato applicando l'attributo <xref:System.FlagsAttribute?displayProperty=fullName> e definendo in modo appropriato i valori in modo che sia possibile eseguirvi operazioni bit per bit `AND`, `OR`, `NOT` e `XOR`.</span><span class="sxs-lookup"><span data-stu-id="65125-132">You create a bit flags enum by applying the <xref:System.FlagsAttribute?displayProperty=fullName> attribute and defining the values appropriately so that `AND`, `OR`, `NOT` and `XOR` bitwise operations can be performed on them.</span></span> <span data-ttu-id="65125-133">In un enum di flag di bit, includere una costante denominata con valore zero, che indica che non sono impostati flag.</span><span class="sxs-lookup"><span data-stu-id="65125-133">In a bit flags enum, include a named constant with a value of zero that means "no flags are set."</span></span> <span data-ttu-id="65125-134">Assegnare a un flag un valore pari a zero solo per indicare che non sono impostati flag.</span><span class="sxs-lookup"><span data-stu-id="65125-134">Do not give a flag a value of zero if it does not mean "no flags are set".</span></span>  
  
 <span data-ttu-id="65125-135">Nell'esempio seguente viene definita un'altra versione dell'enum `Days` denominata `Days2`.</span><span class="sxs-lookup"><span data-stu-id="65125-135">In the following example, another version of the `Days` enum, which is named `Days2`, is defined.</span></span> <span data-ttu-id="65125-136">`Days2` dispone dell'attributo `Flags`. A ogni valore viene assegnata la successiva potenza di 2.</span><span class="sxs-lookup"><span data-stu-id="65125-136">`Days2` has the `Flags` attribute and each value is assigned the next greater power of 2.</span></span> <span data-ttu-id="65125-137">In questo modo è possibile creare una variabile `Days2` il cui valore è `Days2.Tuesday` e `Days2.Thursday`.</span><span class="sxs-lookup"><span data-stu-id="65125-137">This enables you to create a `Days2` variable whose value is `Days2.Tuesday` and `Days2.Thursday`.</span></span>  
  
 <span data-ttu-id="65125-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-138">[!code-cs[csProgGuideEnums#2](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_4.cs)]</span></span>  
  
 <span data-ttu-id="65125-139">Per impostare un flag su un enum, usare l'operatore `OR` bit per bit come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="65125-139">To set a flag on an enum, use the bitwise `OR` operator as shown in the following example:</span></span>  
  
 <span data-ttu-id="65125-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-140">[!code-cs[csProgGuideEnums#6](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_5.cs)]</span></span>  
  
 <span data-ttu-id="65125-141">Per determinare se un flag specifico è impostato, usare l'operatore `AND` bit per bit come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="65125-141">To determine whether a specific flag is set, use a bitwise `AND` operation, as shown in the following example:</span></span>  
  
 <span data-ttu-id="65125-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-142">[!code-cs[csProgGuideEnums#7](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_6.cs)]</span></span>  
  
 <span data-ttu-id="65125-143">Per altre informazioni sugli aspetti da considerare quando si definiscono tipi di enumerazione con l'attributo <xref:System.FlagsAttribute?displayProperty=fullName>, vedere <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="65125-143">For more information about what to consider when you define enumeration types with the <xref:System.FlagsAttribute?displayProperty=fullName> attribute, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a><span data-ttu-id="65125-144">Uso dei metodi System.Enum per individuare e modificare valori enum</span><span class="sxs-lookup"><span data-stu-id="65125-144">Using the System.Enum Methods to Discover and Manipulate Enum Values</span></span>  
 <span data-ttu-id="65125-145">Tutti gli enum sono istanze del tipo <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="65125-145">All enums are instances of the <xref:System.Enum?displayProperty=fullName> type.</span></span> <span data-ttu-id="65125-146">Non è possibile derivare nuove classi da <xref:System.Enum?displayProperty=fullName>, ma è possibile usarne i metodi per individuare informazioni e modificare valori in un'istanza dell'enum.</span><span class="sxs-lookup"><span data-stu-id="65125-146">You cannot derive new classes from <xref:System.Enum?displayProperty=fullName>, but you can use its methods to discover information about and manipulate values in an enum instance.</span></span>  
  
 <span data-ttu-id="65125-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="65125-147">[!code-cs[csProgGuideEnums#5](../../csharp/programming-guide/codesnippet/CSharp/enumeration-types_7.cs)]</span></span>  
  
 <span data-ttu-id="65125-148">Per altre informazioni, vedere <xref:System.Enum?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="65125-148">For more information, see <xref:System.Enum?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="65125-149">È anche possibile creare un nuovo metodo per un enum tramite un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="65125-149">You can also create a new method for an enum by using an extension method.</span></span> <span data-ttu-id="65125-150">Per altre informazioni, vedere [Procedura: Creare un nuovo metodo per una enumerazione (Guida per programmatori C#)](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="65125-150">For more information, see [How to: Create a New Method for an Enumeration](../../csharp/programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="65125-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65125-151">See Also</span></span>  
 <span data-ttu-id="65125-152"><xref:System.Enum?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="65125-152"><xref:System.Enum?displayProperty=fullName></span></span>   
 <span data-ttu-id="65125-153">[Guida per programmatori C#](../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="65125-153">[C# Programming Guide](../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="65125-154">enum</span><span class="sxs-lookup"><span data-stu-id="65125-154">enum</span></span>](../../csharp/language-reference/keywords/enum.md)

