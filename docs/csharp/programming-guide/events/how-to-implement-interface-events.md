---
title: Come implementare gli eventi di interfaccia C# -Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: b84b96245310bce557bcd3865e41cf152e7ae9df
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712338"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Come implementare gli eventi di interfacciaC# (Guida per programmatori)
Un'[interfaccia](../../language-reference/keywords/interface.md) consente di dichiarare un [evento](../../language-reference/keywords/event.md). Nell'esempio seguente viene illustrato come implementare eventi di interfaccia in una classe. Le regole sono le stesse usate per l'implementazione di qualsiasi metodo di interfaccia o proprietà.  
  
## <a name="to-implement-interface-events-in-a-class"></a>Per implementare eventi di interfaccia in una classe  
  
Dichiarare l'evento nella classe e quindi richiamarlo nelle posizioni appropriate.  
  
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
  
## <a name="example"></a>Esempio  
Nell'esempio seguente viene illustrato come gestire la situazione meno comune in cui la classe eredita da due o più interfacce e a ogni interfaccia è associato un evento con lo stesso nome. In questo caso, è necessario fornire un'implementazione di interfaccia esplicita per almeno uno degli eventi. Quando si scrive un'implementazione di interfaccia esplicita per un evento, è anche necessario scrivere le funzioni di accesso agli eventi `add` e `remove`. In genere queste funzioni sono fornite dal compilatore, ma in questo caso il compilatore non è in grado di farlo.  
  
Fornendo funzioni di accesso personalizzate, è possibile specificare se i due eventi sono rappresentati dallo stesso evento nella classe o da eventi diversi. Ad esempio, se gli eventi devono essere generati in momenti diversi secondo le specifiche dell'interfaccia, è possibile associare ogni evento a un'implementazione separata nella classe. Nell'esempio seguente i sottoscrittori determinano l'evento `OnDraw` che riceveranno eseguendo il cast del riferimento della forma su `IShape` o `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Eventi](./index.md)
- [Delegati](../delegates/index.md)
- [Implementazione esplicita dell'interfaccia](../interfaces/explicit-interface-implementation.md)
- [Come generare eventi di classe base nelle classi derivate](./how-to-raise-base-class-events-in-derived-classes.md)
