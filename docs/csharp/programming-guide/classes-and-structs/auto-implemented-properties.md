---
title: Proprietà implementate automaticamente (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 0d32dfd626cb8484e935dd0e8608c2e29d3ecbde
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44228078"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="69dda-102">Proprietà implementate automaticamente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="69dda-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="69dda-103">In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="69dda-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="69dda-104">Consentono inoltre al codice client di creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="69dda-104">They also enable client code to create objects.</span></span> <span data-ttu-id="69dda-105">Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.</span><span class="sxs-lookup"><span data-stu-id="69dda-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69dda-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="69dda-106">Example</span></span>  
 <span data-ttu-id="69dda-107">L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:</span><span class="sxs-lookup"><span data-stu-id="69dda-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 <span data-ttu-id="69dda-108">In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:</span><span class="sxs-lookup"><span data-stu-id="69dda-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="69dda-109">La classe mostrata nell'esempio precedente è modificabile.</span><span class="sxs-lookup"><span data-stu-id="69dda-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="69dda-110">Il codice client può modificare i valori negli oggetti dopo che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="69dda-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="69dda-111">Nelle classi complesse che contengono un comportamento significativo (metodi) oltre ai dati, spesso è necessario disporre di proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="69dda-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="69dda-112">Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../../csharp/language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).</span><span class="sxs-lookup"><span data-stu-id="69dda-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../../csharp/language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="69dda-113">Per altre informazioni, vedere [Procedura: Implementare una classe leggera con proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69dda-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="69dda-114">Gli attributi sono consentiti nelle proprietà implementate automaticamente, ma ovviamente non nei campi sottostanti perché non sono accessibili dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="69dda-114">Attributes are permitted on auto-implemented properties but obviously not on the backing fields since those are not accessible from your source code.</span></span> <span data-ttu-id="69dda-115">Se è necessario usare un attributo nel campo sottostante di una proprietà, è sufficiente creare una normale proprietà.</span><span class="sxs-lookup"><span data-stu-id="69dda-115">If you must use an attribute on the backing field of a property, just create a regular property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dda-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69dda-116">See Also</span></span>

- [<span data-ttu-id="69dda-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="69dda-117">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="69dda-118">Modificatori</span><span class="sxs-lookup"><span data-stu-id="69dda-118">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
