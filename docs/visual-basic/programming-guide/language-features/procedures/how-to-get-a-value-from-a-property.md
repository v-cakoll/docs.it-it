---
title: 'Procedura: ottenere un valore da una proprietà (Visual Basic)'
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
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7161052b9d9b388d8da8bd421c3b220f15037805
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Procedura: ottenere un valore da una proprietà (Visual Basic)
Per recuperare un valore della proprietà di includere il nome della proprietà in un'espressione.  
  
 La proprietà `Get` procedura recupera il valore, ma non chiamare in modo esplicito, in base al nome. Utilizzare la proprietà, esattamente come si utilizzerebbe una variabile. Visual Basic effettua le chiamate alle routine della proprietà.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Per recuperare un valore da una proprietà  
  
1.  Utilizzare il nome della proprietà in un'espressione esattamente come si utilizzerebbe un nome di variabile. È possibile utilizzare una proprietà in qualsiasi punto è possibile utilizzare una variabile o costante.  
  
     oppure  
  
     Utilizzare il nome della proprietà seguente uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.  
  
     Nell'esempio seguente legge il valore di Visual Basic `Now` proprietà, in modo implicito chiamando il relativo `Get` stored procedure.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.  
  
 Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
