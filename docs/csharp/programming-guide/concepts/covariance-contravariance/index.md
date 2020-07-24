---
title: Covarianza e controvarianza (C#)
description: Informazioni sulla covarianza e la controvarianza e sul modo in cui incidono sulla compatibilità dell'assegnazione. Vedere un esempio di codice in cui vengono illustrate le differenze tra di essi.
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: 65c75029c27b6c9a5ddc96f01622b520e8698f55
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105701"
---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="629d6-104">Covarianza e controvarianza (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-104">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="629d6-105">In C#, covarianza e controvarianza abilitano la conversione implicita del riferimento per i tipi di matrice, i tipi delegati e gli argomenti di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="629d6-105">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="629d6-106">La covarianza mantiene la compatibilità dell'assegnazione e la controvarianza la inverte.</span><span class="sxs-lookup"><span data-stu-id="629d6-106">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="629d6-107">Il codice seguente illustra la differenza tra la compatibilità dell'assegnazione, covarianza e controvarianza.</span><span class="sxs-lookup"><span data-stu-id="629d6-107">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.
object obj = str;  
  
// Covariance.
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument
// is assigned to an object instantiated with a less derived type argument.
// Assignment compatibility is preserved.
IEnumerable<object> objects = strings;  
  
// Contravariance.
// Assume that the following method is in the class:
// static void SetObject(object o) { }
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument
// is assigned to an object instantiated with a more derived type argument.
// Assignment compatibility is reversed.
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="629d6-108">La covarianza per le matrici consente la conversione implicita di una matrice di un tipo più derivato in una matrice di un tipo meno derivato.</span><span class="sxs-lookup"><span data-stu-id="629d6-108">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="629d6-109">Ma questa operazione non è indipendente dai tipi, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="629d6-109">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="629d6-110">Il supporto di covarianza e controvarianza per i gruppi di metodi consente la corrispondenza delle firme del metodo con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="629d6-110">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="629d6-111">Ciò consente di assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="629d6-111">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="629d6-112">Per altre informazioni, vedere [Varianza nei delegati (C#)](./variance-in-delegates.md) e [Uso della varianza nei delegati (C#)](./using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="629d6-112">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance in Delegates (C#)](./using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="629d6-113">L'esempio di codice seguente illustra il supporto di covarianza e controvarianza per i gruppi di metodi.</span><span class="sxs-lookup"><span data-stu-id="629d6-113">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="629d6-114">In .NET Framework 4 e versioni successive, C# supporta la covarianza e la controvarianza nelle interfacce e nei delegati generici e consente la conversione implicita di parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="629d6-114">In .NET Framework 4 and later versions, C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="629d6-115">Per altre informazioni, vedere [Varianza nelle interfacce generiche (C#)](./variance-in-generic-interfaces.md) e [Varianza nei delegati (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="629d6-115">For more information, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="629d6-116">L'esempio di codice seguente illustra la conversione implicita del riferimento per le interfacce generiche.</span><span class="sxs-lookup"><span data-stu-id="629d6-116">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="629d6-117">Le interfacce o i delegati generici sono detti *varianti* se i relativi parametri generici vengono dichiarati come covarianti o controvarianti.</span><span class="sxs-lookup"><span data-stu-id="629d6-117">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="629d6-118">C# consente di creare i propri delegati e interfacce varianti.</span><span class="sxs-lookup"><span data-stu-id="629d6-118">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="629d6-119">Per altre informazioni, vedere [Creazione di interfacce generiche varianti (C#)](./creating-variant-generic-interfaces.md) e [Varianza nei delegati (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="629d6-119">For more information, see [Creating Variant Generic Interfaces (C#)](./creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="629d6-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="629d6-120">Related Topics</span></span>  
  
|<span data-ttu-id="629d6-121">Titolo</span><span class="sxs-lookup"><span data-stu-id="629d6-121">Title</span></span>|<span data-ttu-id="629d6-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="629d6-122">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="629d6-123">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-123">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)|<span data-ttu-id="629d6-124">Illustra la covarianza e la controvarianza nelle interfacce generiche e fornisce un elenco di interfacce generiche variant in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="629d6-124">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="629d6-125">Creazione di interfacce generiche varianti (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-125">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)|<span data-ttu-id="629d6-126">Spiega come creare interfacce varianti personalizzate.</span><span class="sxs-lookup"><span data-stu-id="629d6-126">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="629d6-127">Uso della varianza nelle interfacce per le raccolte generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-127">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="629d6-128">Spiega come il supporto di covarianza e controvarianza nelle interfacce <xref:System.Collections.Generic.IEnumerable%601> e <xref:System.IComparable%601> consente di riutilizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="629d6-128">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="629d6-129">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-129">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)|<span data-ttu-id="629d6-130">Illustra la covarianza e la controvarianza nei delegati generici e non generici e offre un elenco di delegati generici varianti in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="629d6-130">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="629d6-131">Uso della varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-131">Using Variance in Delegates (C#)</span></span>](./using-variance-in-delegates.md)|<span data-ttu-id="629d6-132">Spiega come usare il supporto di covarianza e controvarianza nei delegati non generici per la corrispondenza delle firme del metodo con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="629d6-132">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="629d6-133">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="629d6-133">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="629d6-134">Spiega come il supporto di covarianza e controvarianza nei delegati `Func` e `Action` consente di riutilizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="629d6-134">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
