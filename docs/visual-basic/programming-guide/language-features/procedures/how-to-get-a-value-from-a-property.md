---
title: 'Procedura: ottenere un valore da una proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 2c92cd4a869acbb7c8c52fbf4117112967386498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387894"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Procedura: ottenere un valore da una proprietà (Visual Basic)
Per recuperare il valore di una proprietà, è necessario includere il nome della proprietà in un'espressione.  
  
 La routine della proprietà `Get` Recupera il valore, ma non lo chiama in modo esplicito in base al nome. Usare la proprietà esattamente come si farebbe per usare una variabile. Visual Basic esegue le chiamate alle routine della proprietà.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Per recuperare un valore da una proprietà  
  
1. Usare il nome della proprietà in un'espressione nello stesso modo in cui si usa un nome di variabile. È possibile usare una proprietà ovunque sia possibile usare una variabile o una costante.  
  
     -oppure-  
  
     Usare il nome della proprietà che segue il `=` segno di uguale () in un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene letto il valore della `Now` proprietà Visual Basic, chiamando in modo implicito la relativa `Get` routine.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà partecipa all'espressione come una variabile o una costante oppure viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: creare una proprietà](./how-to-create-a-property.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
