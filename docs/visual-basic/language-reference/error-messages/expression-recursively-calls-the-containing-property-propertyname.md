---
title: L'espressione chiama in modo ricorsivo la proprietà '<propertyname>' che la contiene
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698572"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>L'espressione chiama in modo ricorsivo la proprietà' \<propertyname >' che lo contiene
Un'istruzione nella procedura `Set` di una definizione di proprietà archivia un valore nel nome della proprietà.  
  
 L'approccio consigliato per contenere il valore di una proprietà consiste nel definire una variabile `Private` nel contenitore della proprietà e usarla nelle procedure `Get` e `Set`. La procedura `Set` deve quindi archiviare il valore in ingresso in questa variabile `Private`.  
  
 La procedura `Get` si comporta come una procedura `Function`, in modo da poter assegnare un valore al nome della proprietà e restituire il controllo mediante l'istruzione `End Get`. Tuttavia, l'approccio consigliato consiste nell'includere la variabile `Private` come valore in un' [istruzione return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 La procedura `Set` si comporta come una procedura `Sub`, che non restituisce un valore. Pertanto, il nome della procedura o della proprietà non ha un significato speciale in una procedura `Set` e non è possibile archiviarvi un valore.  
  
 Nell'esempio seguente viene illustrato l'approccio che può causare questo errore, seguito dall'approccio consigliato.  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42026  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Riscrivere la definizione della proprietà in modo da usare l'approccio consigliato, come illustrato nell'esempio precedente.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
