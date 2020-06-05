---
title: 'Procedura: dichiarare una proprietà con livelli di accesso misti'
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
ms.openlocfilehash: f0f7aba25888544dfcc093906850ae7ada621182
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388245"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>Procedura: dichiarare una proprietà con livelli di accesso misti (Visual Basic)
Se si desidera che `Get` le `Set` routine e in una proprietà dispongano di livelli di accesso diversi, è possibile utilizzare il livello più permissivo nell' `Property` istruzione e il livello più restrittivo nell' `Get` `Set` istruzione o. Si utilizzano livelli di accesso misti su una proprietà quando si desidera che determinate parti del codice siano in grado di ottenere il valore della proprietà e che alcune altre parti del codice siano in grado di modificare il valore.  
  
 Per altre informazioni sui livelli di accesso, vedere [livelli di accesso in Visual Basic](../declared-elements/access-levels.md).  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>Per dichiarare una proprietà con livelli di accesso misti  
  
1. Dichiarare la proprietà in modo normale e specificare il livello di accesso meno restrittivo, ad esempio, `Public` nell' `Property` istruzione.  
  
2. Dichiarare la `Get` `Set` routine o specificando il livello di accesso più restrittivo, ad esempio `Friend` .  
  
3. Non specificare un livello di accesso nell'altra routine della proprietà. Si presuppone il livello di accesso dichiarato nell' `Property` istruzione. È possibile limitare l'accesso solo a una delle routine della proprietà.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     Nell'esempio precedente, la `Get` procedura ha lo stesso `Protected` accesso della proprietà stessa, mentre la `Set` stored procedure ha `Private` accesso. Una classe derivata da `employee` può leggere il `salary` valore, ma solo la `employee` classe può impostarla.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: creare una proprietà](./how-to-create-a-property.md)
- [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
