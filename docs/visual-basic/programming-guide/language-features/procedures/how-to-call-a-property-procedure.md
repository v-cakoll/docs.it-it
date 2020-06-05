---
title: 'Procedura: chiamare una routine di proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 006961a0f1d4be6b0d52be5bc273dad9733bfe56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388699"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Procedura: chiamare una routine di proprietà (Visual Basic)
È possibile chiamare una routine di proprietà archiviando un valore nella proprietà o recuperando il relativo valore. È possibile accedere a una proprietà nello stesso modo in cui si accede a una variabile.  
  
 La routine della proprietà `Set` Archivia un valore e la relativa `Get` routine Recupera il valore. Tuttavia, queste procedure non vengono chiamate in modo esplicito in base al nome. È possibile utilizzare la proprietà in un'istruzione di assegnazione o in un'espressione, così come si archivia o si recupera il valore di una variabile. Visual Basic esegue le chiamate alle routine della proprietà.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Per chiamare la routine Get di una proprietà  
  
1. Usare il nome della proprietà in un'espressione nello stesso modo in cui si usa un nome di variabile. È possibile usare una proprietà ovunque sia possibile usare una variabile o una costante.  
  
     -oppure-  
  
     Usare il nome della proprietà che segue il `=` segno di uguale () in un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene letto il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> proprietà, chiamando in modo implicito la relativa `Get` routine.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà partecipa all'espressione come una variabile o una costante oppure viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Per chiamare la routine set di una proprietà  
  
1. Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene impostato il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> proprietà, chiamando in modo implicito la `Set` routine.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: creare una proprietà](./how-to-create-a-property.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
- [Istruzione Get](../../../language-reference/statements/get-statement.md)
- [Istruzione set](../../../language-reference/statements/set-statement.md)
