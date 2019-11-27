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
ms.openlocfilehash: 52e6c62ffb81c480ccc1abf06f04eb780218dbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340559"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Procedura: chiamare una routine di proprietà (Visual Basic)
È possibile chiamare una routine di proprietà archiviando un valore nella proprietà o recuperando il relativo valore. È possibile accedere a una proprietà nello stesso modo in cui si accede a una variabile.  
  
 La stored procedure `Set` della proprietà archivia un valore e la relativa routine `Get` Recupera il valore. Tuttavia, queste procedure non vengono chiamate in modo esplicito in base al nome. È possibile utilizzare la proprietà in un'istruzione di assegnazione o in un'espressione, così come si archivia o si recupera il valore di una variabile. Visual Basic esegue le chiamate alle routine della proprietà.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Per chiamare la routine Get di una proprietà  
  
1. Usare il nome della proprietà in un'espressione nello stesso modo in cui si usa un nome di variabile. È possibile usare una proprietà ovunque sia possibile usare una variabile o una costante.  
  
     -oppure-  
  
     Usare il nome della proprietà che segue il segno di uguale (`=`) in un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene letto il valore della proprietà <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>, chiamando in modo implicito la relativa procedura di `Get`.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà partecipa all'espressione come una variabile o una costante oppure viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Per chiamare la routine set di una proprietà  
  
1. Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene impostato il valore della proprietà <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>, chiamando in modo implicito la routine `Set`.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
- [Istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md)
