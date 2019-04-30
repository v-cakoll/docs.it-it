---
title: 'Procedura: Esporre le proprietà dei controlli costitutivi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: 44b96218e674c754a1985f2f22a36707cd1776b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941375"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="9a20a-102">Procedura: Esporre le proprietà dei controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="9a20a-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="9a20a-103">I controlli che costituiscono un controllo composito sono detti *controlli costitutivi*.</span><span class="sxs-lookup"><span data-stu-id="9a20a-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="9a20a-104">Questi controlli sono in genere dichiarati privati e pertanto non sono accessibile dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="9a20a-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="9a20a-105">Se si desidera rendere disponibili le proprietà di questi controlli per futuri utenti, è necessario esporli all'utente.</span><span class="sxs-lookup"><span data-stu-id="9a20a-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="9a20a-106">Viene esposta una proprietà di un controllo che costituiscono la creazione di una proprietà nel controllo utente e usando il `get` e `set` pubbliche della proprietà per rendere effettiva la modifica della proprietà privata del controllo che lo costituiscono.</span><span class="sxs-lookup"><span data-stu-id="9a20a-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="9a20a-107">Si consideri un controllo utente ipotetico con un pulsante che costituiscono denominato `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="9a20a-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="9a20a-108">In questo esempio, quando l'utente richiede la `ConstituentButtonBackColor` proprietà, il valore archiviato nel <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` viene recapitato.</span><span class="sxs-lookup"><span data-stu-id="9a20a-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="9a20a-109">Quando l'utente viene assegnato un valore per questa proprietà, tale valore viene passato automaticamente al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` e il `set` eseguito codice che modifica il colore di `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="9a20a-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="9a20a-110">Nell'esempio seguente viene illustrato come esporre il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pulsante che costituiscono:</span><span class="sxs-lookup"><span data-stu-id="9a20a-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="9a20a-111">Per esporre una proprietà di un controllo che lo costituiscono</span><span class="sxs-lookup"><span data-stu-id="9a20a-111">To expose a property of a constituent control</span></span>  
  
1. <span data-ttu-id="9a20a-112">Creare una proprietà pubblica per il controllo utente.</span><span class="sxs-lookup"><span data-stu-id="9a20a-112">Create a public property for your user control.</span></span>  
  
2. <span data-ttu-id="9a20a-113">Nel `get` sezione della proprietà, scrivere codice che recupera il valore della proprietà che si desidera esporre.</span><span class="sxs-lookup"><span data-stu-id="9a20a-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3. <span data-ttu-id="9a20a-114">Nel `set` sezione della proprietà, scrivere codice che passa il valore della proprietà alla proprietà esposta del controllo che lo costituiscono.</span><span class="sxs-lookup"><span data-stu-id="9a20a-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a20a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a20a-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="9a20a-116">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="9a20a-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="9a20a-117">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="9a20a-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
