---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 212fdde3a5ecc8b0a43e33bec3537bd57b1387e9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419411"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="15ae9-102">Proprietà implementate automaticamente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="15ae9-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="15ae9-103">In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="15ae9-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="15ae9-104">Consentono inoltre al codice client di creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="15ae9-104">They also enable client code to create objects.</span></span> <span data-ttu-id="15ae9-105">Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.</span><span class="sxs-lookup"><span data-stu-id="15ae9-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15ae9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="15ae9-106">Example</span></span>  
 <span data-ttu-id="15ae9-107">L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:</span><span class="sxs-lookup"><span data-stu-id="15ae9-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="15ae9-108">In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:</span><span class="sxs-lookup"><span data-stu-id="15ae9-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="15ae9-109">La classe mostrata nell'esempio precedente è modificabile.</span><span class="sxs-lookup"><span data-stu-id="15ae9-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="15ae9-110">Il codice client può modificare i valori negli oggetti dopo che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="15ae9-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="15ae9-111">Nelle classi complesse che contengono un comportamento significativo (metodi) oltre ai dati, spesso è necessario disporre di proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="15ae9-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="15ae9-112">Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).</span><span class="sxs-lookup"><span data-stu-id="15ae9-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="15ae9-113">Per altre informazioni, vedere [Procedura: Implementare una classe leggera con proprietà implementate automaticamente](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="15ae9-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ae9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15ae9-114">See also</span></span>

- [<span data-ttu-id="15ae9-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="15ae9-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="15ae9-116">Modificatori</span><span class="sxs-lookup"><span data-stu-id="15ae9-116">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
