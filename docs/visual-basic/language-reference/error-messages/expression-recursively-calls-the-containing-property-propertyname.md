---
title: L'espressione chiama in modo ricorsivo la proprietà '<propertyname>' che la contiene
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: a758d05cca5ca71943b0ef08184aef5b2c457739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836844"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>Espressione in modo ricorsivo chiama la proprietà che contiene '\<NomeProprietà >'
Un'istruzione all'interno di `Set` routine di una definizione di proprietà archivia un valore nel nome della proprietà.  
  
 L'approccio consigliato per contenere il valore di una proprietà consiste nel definire un `Private` variabile nel contenitore della proprietà e utilizzarlo in entrambe le `Get` e `Set` procedure. Il `Set` routine deve quindi archiviare il valore in ingresso in questo `Private` variabile.  
  
 Il `Get` procedure si comporta come un `Function` routine, in modo che può assegnare un valore per il nome della proprietà e restituire il controllo in corrispondenza di `End Get` istruzione. L'approccio consigliato, tuttavia, è di includere il `Private` variabile come valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Il `Set` routine si comporta come un `Sub` routine, che non restituisce un valore. Pertanto, il nome della proprietà o routine ha alcun significato particolare all'interno di un `Set` ed è possibile archiviare un valore al suo interno.  
  
 Nell'esempio seguente viene illustrato l'approccio che può causare questo errore, aggiungendo l'approccio consigliato.  
  
```  
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
  
-   Riscrivere la definizione di proprietà per utilizzare l'approccio consigliato, come illustrato nell'esempio precedente.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
