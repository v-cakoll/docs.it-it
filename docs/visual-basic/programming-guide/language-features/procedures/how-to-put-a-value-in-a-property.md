---
title: 'Procedura: inserire un valore in una proprietà (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00303b290e324612ad3ac7af673690b4cf4e15
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>Procedura: inserire un valore in una proprietà (Visual Basic)
Archiviare un valore in una proprietà inserendo il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
 La proprietà `Set` procedure archivia un valore, ma non chiamare in modo esplicito, in base al nome. Utilizzare la proprietà, esattamente come si utilizzerebbe una variabile. Visual Basic effettua le chiamate alle routine della proprietà.  
  
### <a name="to-store-a-value-in-a-property"></a>Per archiviare un valore in una proprietà  
  
1.  Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.  
  
     Nell'esempio seguente imposta il valore di Visual Basic `TimeOfDay` proprietà a mezzogiorno, chiamata di implicitamente relativo `Set` stored procedure.  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
4.  Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
