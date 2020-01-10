---
title: Proprietà implementate automaticamente - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 76f16a66fbc01a6a69d91136cfbfe5805b91aea3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705639"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="5c1d4-102">Proprietà implementate automaticamente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5c1d4-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="5c1d4-103">In C# 3.0 e versioni successive, le proprietà implementate automaticamente rendono più concisa la dichiarazione di proprietà quando nelle funzioni di accesso della proprietà non è necessaria alcuna logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="5c1d4-104">Consentono inoltre al codice client di creare oggetti.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-104">They also enable client code to create objects.</span></span> <span data-ttu-id="5c1d4-105">Quando si dichiara una proprietà come mostrato nel seguente esempio, il compilatore crea un campo sottostante privato anonimo accessibile solo tramite le funzioni di accesso `get` e `set` della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c1d4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c1d4-106">Example</span></span>  
 <span data-ttu-id="5c1d4-107">L'esempio seguente mostra una classe semplice con alcune proprietà implementate automaticamente:</span><span class="sxs-lookup"><span data-stu-id="5c1d4-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="5c1d4-108">In C# 6 e versioni successive, è possibile inizializzare le proprietà implementate automaticamente in modo simile ai campi:</span><span class="sxs-lookup"><span data-stu-id="5c1d4-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="5c1d4-109">La classe mostrata nell'esempio precedente è modificabile.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="5c1d4-110">Il codice client può modificare i valori negli oggetti dopo che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="5c1d4-111">Nelle classi complesse che contengono un comportamento significativo (metodi) oltre ai dati, spesso è necessario disporre di proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="5c1d4-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="5c1d4-112">Tuttavia, per le classi o gli struct di piccole dimensioni che incapsulano solo un set di valori (dati) e non hanno comportamenti oppure hanno comportamenti limitati, è consigliabile rendere gli oggetti non modificabili dichiarando la funzione di accesso set come [private](../../language-reference/keywords/private.md) (non modificabile dai consumer) o dichiarando solo una funzione di accesso get (non modificabile, tranne che nel costruttore).</span><span class="sxs-lookup"><span data-stu-id="5c1d4-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="5c1d4-113">Per ulteriori informazioni, vedere [come implementare una classe Lightweight con proprietà implementate automaticamente](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5c1d4-113">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c1d4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c1d4-114">See also</span></span>

- [<span data-ttu-id="5c1d4-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5c1d4-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="5c1d4-116">Modificatori</span><span class="sxs-lookup"><span data-stu-id="5c1d4-116">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
