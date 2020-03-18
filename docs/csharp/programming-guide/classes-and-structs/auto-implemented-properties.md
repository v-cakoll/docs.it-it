---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 791455c1eaef752da2b551e20187d390ca6c65e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170325"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="e16a7-102">Proprietà implementate automaticamente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e16a7-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="e16a7-103">In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="e16a7-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="e16a7-104">Consentono inoltre al codice client di creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="e16a7-104">They also enable client code to create objects.</span></span> <span data-ttu-id="e16a7-105">Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e16a7-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="e16a7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e16a7-106">Example</span></span>

<span data-ttu-id="e16a7-107">L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e16a7-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="e16a7-108">Non è possibile dichiarare proprietà implementate automaticamente nelle interfacce.</span><span class="sxs-lookup"><span data-stu-id="e16a7-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="e16a7-109">Le proprietà implementate automaticamente dichiarano un campo di backup dell'istanza privata e le interfacce non possono dichiarare i campi di istanza.</span><span class="sxs-lookup"><span data-stu-id="e16a7-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="e16a7-110">La dichiarazione di una proprietà in un'interfaccia senza definire un corpo dichiara una proprietà con funzioni di accesso che deve essere implementata da ogni tipo che implementa tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e16a7-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="e16a7-111">In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:</span><span class="sxs-lookup"><span data-stu-id="e16a7-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="e16a7-112">La classe mostrata nell'esempio precedente è modificabile.</span><span class="sxs-lookup"><span data-stu-id="e16a7-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="e16a7-113">Il codice client può modificare i valori negli oggetti dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="e16a7-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="e16a7-114">Nelle classi complesse che contengono un comportamento significativo (metodi) e dati, è spesso necessario disporre di proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="e16a7-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="e16a7-115">Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).</span><span class="sxs-lookup"><span data-stu-id="e16a7-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="e16a7-116">Per ulteriori informazioni, vedere [Come implementare una classe leggera con proprietà implementate automaticamente](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e16a7-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e16a7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e16a7-117">See also</span></span>

- [<span data-ttu-id="e16a7-118">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e16a7-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="e16a7-119">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e16a7-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
