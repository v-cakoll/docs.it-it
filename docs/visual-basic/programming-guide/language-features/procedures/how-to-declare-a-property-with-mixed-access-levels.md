---
title: 'Procedura: Dichiarare una proprietà con livelli di accesso misti (Visual Basic)'
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
ms.openlocfilehash: d2b1a80863fe29901554b4912acbbfbdfdab4122
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972586"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Procedura: Dichiarare una proprietà con livelli di accesso misti (Visual Basic)
Se si desidera che il `Get` e `Set` procedure su una proprietà per avere diversi livelli di accesso, è possibile usare il livello più ampio nel `Property` istruzione e il livello più restrittivo in entrambi il `Get` o `Set` istruzione. Si usano livelli di accesso misti su una proprietà quando si desidera che alcune parti del codice sia in grado di ottenere il valore della proprietà e alcune altre parti del codice sia in grado di modificare il valore.  
  
 Per altre informazioni sui livelli di accesso, vedere [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Per dichiarare una proprietà con livelli di accesso misti  
  
1.  Dichiarare la proprietà in modo normale e specificare il livello di accesso meno restrittivo (ad esempio `Public`) nel `Property` istruzione.  
  
2.  Dichiarare uno il `Get` o il `Set` procedura specificando il livello di accesso più restrittivo (ad esempio `Friend`).  
  
3.  Non specificare un livello di accesso nella routine della proprietà. Presuppone che il livello di accesso dichiarato nel `Property` istruzione. È possibile limitare l'accesso solo su una delle routine della proprietà.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     Nell'esempio precedente, il `Get` procedure con lo stesso `Protected` accesso della proprietà stessa, mentre le `Set` routine ha `Private` accesso. Una classe derivata da `employee` può leggere il `salary` valore, ma solo il `employee` classe possibile impostarlo.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
