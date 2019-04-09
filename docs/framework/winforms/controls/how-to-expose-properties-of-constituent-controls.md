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
ms.openlocfilehash: 750caa1f45f870e63a5b7ccbe0c309e6fb0b3178
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106353"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Procedura: Esporre le proprietà dei controlli costitutivi
I controlli che costituiscono un controllo composito sono detti *controlli costitutivi*. Questi controlli sono in genere dichiarati privati e pertanto non sono accessibile dallo sviluppatore. Se si desidera rendere disponibili le proprietà di questi controlli per futuri utenti, è necessario esporli all'utente. Viene esposta una proprietà di un controllo che costituiscono la creazione di una proprietà nel controllo utente e usando il `get` e `set` pubbliche della proprietà per rendere effettiva la modifica della proprietà privata del controllo che lo costituiscono.  
  
 Si consideri un controllo utente ipotetico con un pulsante che costituiscono denominato `MyButton`. In questo esempio, quando l'utente richiede la `ConstituentButtonBackColor` proprietà, il valore archiviato nel <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` viene recapitato. Quando l'utente viene assegnato un valore per questa proprietà, tale valore viene passato automaticamente al <xref:System.Windows.Forms.Control.BackColor%2A> proprietà di `MyButton` e il `set` eseguito codice che modifica il colore di `MyButton`.  
  
 Nell'esempio seguente viene illustrato come esporre il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà del pulsante che costituiscono:  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>Per esporre una proprietà di un controllo che lo costituiscono  
  
1.  Creare una proprietà pubblica per il controllo utente.  
  
2.  Nel `get` sezione della proprietà, scrivere codice che recupera il valore della proprietà che si desidera esporre.  
  
3.  Nel `set` sezione della proprietà, scrivere codice che passa il valore della proprietà alla proprietà esposta del controllo che lo costituiscono.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
