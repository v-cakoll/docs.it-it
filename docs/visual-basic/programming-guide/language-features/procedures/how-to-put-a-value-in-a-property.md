---
title: 'Procedura: Inserire un valore in una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: d40ca98f94f410bb20c8df0e7f1a3f216cf53bf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589165"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Procedura: Inserire un valore in una proprietà (Visual Basic)
Archiviare un valore in una proprietà inserendo il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
 La proprietà `Set` procedure archivia un valore, ma è non chiamare in modo esplicito in base al nome. Utilizzare la proprietà esattamente come si utilizzerebbe una variabile. Visual Basic effettua le chiamate alle routine della proprietà.  
  
### <a name="to-store-a-value-in-a-property"></a>Per archiviare un valore in una proprietà  
  
1.  Usare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore di Visual Basic `TimeOfDay` proprietà a mezzogiorno, chiamare in modo implicito il `Set` procedure.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Se la proprietà accetta argomenti, seguire il nome della proprietà tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
4.  Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
