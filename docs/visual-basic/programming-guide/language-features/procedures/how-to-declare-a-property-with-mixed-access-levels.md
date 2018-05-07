---
title: 'Procedura: dichiarare una proprietà con livelli di accesso misti (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: 8d25086fe6f8b5f5300006466ef49782cb065edf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Procedura: dichiarare una proprietà con livelli di accesso misti (Visual Basic)
Se si desidera il `Get` e `Set` procedure su una proprietà di diversi livelli di accesso, è possibile utilizzare il livello più permissivo di `Property` istruzione e il livello più restrittivo in uno il `Get` o `Set` istruzione. Utilizzare i livelli di accesso misti su una proprietà quando si desidera che determinate parti del codice in grado di ottenere il valore della proprietà e altre parti del codice in grado di modificare il valore.  
  
 Per ulteriori informazioni sui livelli di accesso, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Per dichiarare una proprietà con livelli di accesso misti  
  
1.  Dichiarare la proprietà nel modo consueto e specificare il livello di accesso meno restrittivo (ad esempio `Public`) nei `Property` istruzione.  
  
2.  Dichiarare uno di `Get` o `Set` procedura specificando il livello di accesso più restrittivo (ad esempio `Friend`).  
  
3.  Non specificare un livello di accesso nella routine della proprietà. Si presuppone che il livello di accesso dichiarato nella `Property` istruzione. È possibile limitare l'accesso solo su una delle routine della proprietà.  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     Nell'esempio precedente, il `Get` procedura ha lo stesso `Protected` accesso della proprietà stessa, mentre il `Set` routine ha `Private` accesso. Una classe derivata da `employee` può leggere il `salary` valore, ma solo la `employee` classe impostare la proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
