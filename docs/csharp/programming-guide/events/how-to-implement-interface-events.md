---
title: 'Procedura: Implementare gli eventi di interfaccia (Guida per programmatori C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: 3620a3e11553bdd6878126388b612113b5722e89
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863661"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="e7ef1-102">Procedura: Implementare gli eventi di interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e7ef1-102">How to: Implement Interface Events (C# Programming Guide)</span></span>
<span data-ttu-id="e7ef1-103">Un'[interfaccia](../../../csharp/language-reference/keywords/interface.md) consente di dichiarare un [evento](../../../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="e7ef1-103">An [interface](../../../csharp/language-reference/keywords/interface.md) can declare an [event](../../../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="e7ef1-104">Nell'esempio seguente viene illustrato come implementare eventi di interfaccia in una classe.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="e7ef1-105">Le regole sono le stesse usate per l'implementazione di qualsiasi metodo di interfaccia o proprietà.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="e7ef1-106">Per implementare eventi di interfaccia in una classe</span><span class="sxs-lookup"><span data-stu-id="e7ef1-106">To implement interface events in a class</span></span>  
  
<span data-ttu-id="e7ef1-107">Dichiarare l'evento nella classe e quindi richiamarlo nelle posizioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs   
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.   
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="e7ef1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7ef1-108">Example</span></span>  
<span data-ttu-id="e7ef1-109">Nell'esempio seguente viene illustrato come gestire la situazione meno comune in cui la classe eredita da due o più interfacce e a ogni interfaccia è associato un evento con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="e7ef1-110">In questo caso, è necessario fornire un'implementazione di interfaccia esplicita per almeno uno degli eventi.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="e7ef1-111">Quando si scrive un'implementazione di interfaccia esplicita per un evento, è anche necessario scrivere le funzioni di accesso agli eventi `add` e `remove`.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="e7ef1-112">In genere queste funzioni sono fornite dal compilatore, ma in questo caso il compilatore non è in grado di farlo.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="e7ef1-113">Fornendo funzioni di accesso personalizzate, è possibile specificare se i due eventi sono rappresentati dallo stesso evento nella classe o da eventi diversi.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="e7ef1-114">Ad esempio, se gli eventi devono essere generati in momenti diversi secondo le specifiche dell'interfaccia, è possibile associare ogni evento a un'implementazione separata nella classe.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="e7ef1-115">Nell'esempio seguente i sottoscrittori determinano l'evento `OnDraw` che riceveranno eseguendo il cast del riferimento della forma su `IShape` o `IDrawingObject`.</span><span class="sxs-lookup"><span data-stu-id="e7ef1-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[WrapTwoInterfaceEvents](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs#everything)]
  
## <a name="see-also"></a><span data-ttu-id="e7ef1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7ef1-116">See Also</span></span>

- [<span data-ttu-id="e7ef1-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e7ef1-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e7ef1-118">Eventi</span><span class="sxs-lookup"><span data-stu-id="e7ef1-118">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="e7ef1-119">Delegati</span><span class="sxs-lookup"><span data-stu-id="e7ef1-119">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="e7ef1-120">Implementazione esplicita dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="e7ef1-120">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
- [<span data-ttu-id="e7ef1-121">Procedura: Generare eventi di classe base nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="e7ef1-121">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
