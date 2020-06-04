---
title: L'espressione chiama in modo ricorsivo la proprietà '<propertyname>' che la contiene
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: e3a9f4cf2f4105d2c449813bf0c593860df7d1f0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409530"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>L'espressione chiama in modo ricorsivo la proprietà '\<propertyname>' che la contiene
Un'istruzione nella `Set` procedura di una definizione di proprietà archivia un valore nel nome della proprietà.  
  
 L'approccio consigliato per contenere il valore di una proprietà consiste nel definire una `Private` variabile nel contenitore della proprietà e usarla in entrambe le `Get` routine e `Set` . La `Set` stored procedure deve quindi archiviare il valore in ingresso in questa `Private` variabile.  
  
 La `Get` procedura si comporta come una `Function` routine, quindi può assegnare un valore al nome della proprietà e restituire il controllo mediante l' `End Get` istruzione. Tuttavia, l'approccio consigliato consiste nell'includere la `Private` variabile come valore in un' [istruzione Return](../statements/return-statement.md).  
  
 La `Set` procedura si comporta come una `Sub` routine che non restituisce un valore. Pertanto, il nome della procedura o della proprietà non ha un significato speciale all'interno di una `Set` routine e non è possibile archiviarvi un valore.  
  
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

- [Routine Property](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Istruzione set](../statements/set-statement.md)
