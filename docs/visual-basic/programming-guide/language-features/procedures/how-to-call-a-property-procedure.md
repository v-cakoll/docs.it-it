---
title: "Procedura: chiamare una routine di proprietà (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>Procedura: chiamare una routine di proprietà (Visual Basic)
Per chiamare una routine di proprietà per archiviare un valore nella proprietà o recuperarne il valore. Si accede alla proprietà allo stesso modo accedere a una variabile.  
  
 La proprietà `Set` routine memorizza un valore e il relativo `Get` procedura recupera il valore. Tuttavia, non chiamare in modo esplicito queste procedure in base al nome. Utilizzare la proprietà in un'istruzione di assegnazione o un'espressione, così come viene archiviato o recuperare il valore di una variabile. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]effettua le chiamate alle routine della proprietà.  
  
### <a name="to-call-a-propertys-get-procedure"></a>Per chiamare routine Get di una proprietà  
  
1.  Utilizzare il nome della proprietà in un'espressione esattamente come si utilizzerebbe un nome di variabile. È possibile utilizzare una proprietà in qualsiasi punto è possibile utilizzare una variabile o costante.  
  
     -oppure-  
  
     Utilizzare il nome della proprietà seguente uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.  
  
     Nell'esempio seguente viene letto il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> proprietà, la chiamata in modo implicito il `Get` stored procedure.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
### <a name="to-call-a-propertys-set-procedure"></a>Per chiamare una proprietà dell'insieme di procedure  
  
1.  Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> proprietà, la chiamata in modo implicito il `Set` stored procedure.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)  
 [Istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [Istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md)
