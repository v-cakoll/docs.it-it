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
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015865"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Procedura: Esporre le proprietà dei controlli costitutivi
I controlli che costituiscono un controllo composto sono denominati *controlli costitutivi*. Questi controlli sono normalmente dichiarati privati e pertanto non è possibile accedervi dallo sviluppatore. Se si desidera rendere le proprietà di questi controlli disponibili per gli utenti futuri, è necessario esporle all'utente. Una proprietà di un controllo costitutivo viene esposta creando una proprietà nel controllo utente e utilizzando le `get` funzioni di accesso e `set` di tale proprietà per applicare la modifica alla proprietà privata del controllo costitutivo.

 Si consideri un ipotetico controllo utente con `MyButton`un pulsante costitutivo denominato. In questo esempio, quando l'utente richiede la `ConstituentButtonBackColor` proprietà, viene recapitato il <xref:System.Windows.Forms.Control.BackColor%2A> valore archiviato `MyButton` nella proprietà di. Quando l'utente assegna un valore a questa proprietà, tale valore viene <xref:System.Windows.Forms.Control.BackColor%2A> passato automaticamente alla proprietà di `MyButton` e il `set` codice viene eseguito, modificando il colore di `MyButton`.

 Nell'esempio seguente viene illustrato come esporre la <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pulsante costituente:

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

### <a name="to-expose-a-property-of-a-constituent-control"></a>Per esporre una proprietà di un controllo costitutivo

1. Creare una proprietà pubblica per il controllo utente.

2. `get` Nella sezione della proprietà scrivere il codice che recupera il valore della proprietà che si desidera esporre.

3. `set` Nella sezione della proprietà scrivere il codice che passa il valore della proprietà alla proprietà esposta del controllo costitutivo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
