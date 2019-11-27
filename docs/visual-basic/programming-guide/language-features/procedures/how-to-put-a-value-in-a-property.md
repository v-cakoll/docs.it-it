---
title: 'Procedura: inserire un valore in una proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ad0d0e81f94dd3dead50f21c3bd6ff580c004dd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346051"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Procedura: inserire un valore in una proprietà (Visual Basic)
Per archiviare un valore in una proprietà, inserire il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
 La stored procedure `Set` della proprietà archivia un valore, ma non lo chiama in modo esplicito in base al nome. Usare la proprietà esattamente come si farebbe per usare una variabile. Visual Basic esegue le chiamate alle routine della proprietà.  
  
### <a name="to-store-a-value-in-a-property"></a>Per archiviare un valore in una proprietà  
  
1. Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente il valore della proprietà Visual Basic `TimeOfDay` viene impostato su mezzogiorno, chiamando in modo implicito la relativa procedura di `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
4. Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
