---
title: 'Procedura: identificare un tipo nullable (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 610ed18308df02c5632361cd09ef94330dea598b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="45994-102">Procedura: identificare un tipo nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="45994-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="45994-103">È possibile usare l'operatore [typeof](../../../csharp/language-reference/keywords/typeof.md) C# per creare un oggetto <xref:System.Type> che rappresenta un tipo nullable:</span><span class="sxs-lookup"><span data-stu-id="45994-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="45994-104">È anche possibile usare le classi e i metodi dello spazio dei nomi <xref:System.Reflection> per generare oggetti <xref:System.Type> che rappresentano tipi nullable.</span><span class="sxs-lookup"><span data-stu-id="45994-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="45994-105">Se tuttavia si prova a ottenere informazioni sul tipo dalle variabili nullable in fase di esecuzione usando il metodo <xref:System.Object.GetType%2A> o l'operatore `is`, il risultato è un oggetto <xref:System.Type> che rappresenta il tipo sottostante, non il tipo nullable stesso.</span><span class="sxs-lookup"><span data-stu-id="45994-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="45994-106">La chiamata di `GetType` su un tipo nullable causa l'esecuzione di un'operazione di conversione boxing quando il tipo viene convertito implicitamente in <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="45994-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="45994-107">Pertanto, <xref:System.Object.GetType%2A> restituisce sempre un oggetto <xref:System.Type> che rappresenta il tipo sottostante, non il tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="45994-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="45994-108">L'operatore C# [is](../../../csharp/language-reference/keywords/is.md) funziona anche sul tipo sottostante di un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="45994-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="45994-109">Non è quindi possibile usare `is` per determinare se una variabile è un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="45994-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="45994-110">L'esempio seguente mostra che l'operatore `is` tratta una variabile Nullable\<int> come tipo int.</span><span class="sxs-lookup"><span data-stu-id="45994-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="45994-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="45994-111">Example</span></span>  
 <span data-ttu-id="45994-112">Usare il codice seguente per determinare se un oggetto <xref:System.Type> rappresenta un tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="45994-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="45994-113">Tenere presente che questo codice restituisce sempre false se l'oggetto `Type` è stato restituito da una chiamata a <xref:System.Object.GetType%2A>, come illustrato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="45994-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="45994-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45994-114">See Also</span></span>  
 [<span data-ttu-id="45994-115">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="45994-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="45994-116">Conversione boxing dei tipi nullable</span><span class="sxs-lookup"><span data-stu-id="45994-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
