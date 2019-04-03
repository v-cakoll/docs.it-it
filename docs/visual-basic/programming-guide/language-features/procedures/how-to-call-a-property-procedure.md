---
title: 'Procedura: Chiamare una routine di proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 7b85239f80b4bfa87d1dbb1e3207e63d0cef7eeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827211"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Procedura: Chiamare una routine di proprietà (Visual Basic)
Si chiama una routine di proprietà per archiviare un valore nella proprietà o recuperarne il valore. Si accede a una proprietà allo stesso modo accedere a una variabile.  
  
 La proprietà `Set` procedure archivia un valore e il relativo `Get` procedura recupera il valore. Tuttavia, non chiamare in modo esplicito queste procedure in base al nome. Utilizzare la proprietà in un'istruzione di assegnazione o un'espressione, esattamente come si sarebbe archiviare o recuperare il valore di una variabile. Visual Basic effettua le chiamate alle routine della proprietà.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Per chiamare routine Get della proprietà  
  
1.  Usare il nome della proprietà in un'espressione simile a quello è necessario usare un nome di variabile. È possibile usare una proprietà in qualsiasi punto è possibile usare una variabile o una costante.  
  
     -oppure-  
  
     Usare il nome della proprietà seguente uguali (`=`) Accedi a un'istruzione di assegnazione.  
  
     Nell'esempio seguente legge il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> proprietà, chiamare in modo implicito relativo `Get` procedure.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  Se la proprietà accetta argomenti, seguire il nome della proprietà tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Per chiamare una proprietà del Set di procedure  
  
1.  Usare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> proprietà, chiamare in modo implicito il `Set` procedure.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2.  Se la proprietà accetta argomenti, seguire il nome della proprietà tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
- [Istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)
- [Istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md)
