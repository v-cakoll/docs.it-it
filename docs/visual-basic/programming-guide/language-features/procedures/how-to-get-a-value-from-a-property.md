---
title: 'Procedura: Ottenere un valore da una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 7dbc9d926ae937dd032c0c054bde440037ab9f0d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842915"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Procedura: Ottenere un valore da una proprietà (Visual Basic)
Per recuperare un valore della proprietà di includere il nome della proprietà in un'espressione.  
  
 La proprietà `Get` procedura recupera il valore, ma è non chiamare in modo esplicito in base al nome. Utilizzare la proprietà esattamente come si utilizzerebbe una variabile. Visual Basic effettua le chiamate alle routine della proprietà.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Per recuperare un valore da una proprietà  
  
1.  Usare il nome della proprietà in un'espressione simile a quello è necessario usare un nome di variabile. È possibile usare una proprietà in qualsiasi punto è possibile usare una variabile o una costante.  
  
     -oppure-  
  
     Usare il nome della proprietà seguente uguali (`=`) Accedi a un'istruzione di assegnazione.  
  
     Nell'esempio seguente legge il valore di Visual Basic `Now` proprietà, chiamare in modo implicito il `Get` procedure.  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  Se la proprietà accetta argomenti, seguire il nome della proprietà tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
