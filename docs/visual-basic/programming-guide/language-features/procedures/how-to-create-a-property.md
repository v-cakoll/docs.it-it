---
title: 'Procedura: creare una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 6e3faed9880b6417f17ab8fe84bc5162e803c437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656243"
---
# <a name="how-to-create-a-property-visual-basic"></a>Procedura: creare una proprietà (Visual Basic)
Una proprietà definizione racchiusa tra una `Property` istruzione e un `End Property` istruzione. In questa definizione è definire un `Get` procedure, un `Set` procedure o entrambi. Il codice della proprietà si trova all'interno di queste procedure.  
  
 Il `Get` procedura recupera il valore della proprietà e `Set` routine memorizza un valore. Se si desidera che la proprietà di accesso in lettura/scrittura, è necessario definire entrambe le procedure. Per una proprietà di sola lettura, si definisce solo `Get`, e per una proprietà di sola scrittura, definire solo `Set`.  
  
### <a name="to-create-a-property"></a>Per creare una proprietà  
  
1.  All'esterno di qualsiasi proprietà o routine, utilizzare un [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md), seguito da un `End Property` istruzione.  
  
2.  Se la proprietà accetta parametri, seguire la `Property` (parola chiave) con il nome della routine, quindi l'elenco di parametri tra parentesi.  
  
3.  Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore della proprietà. È necessario specificare il tipo di dati anche per una proprietà di sola scrittura.  
  
4.  Aggiungere `Get` e `Set` procedure, come appropriato. Vedere le indicazioni riportate di seguito.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Per creare una routine Get che recupera un valore della proprietà  
  
1.  Tra le `Property` e `End Property` istruzioni, scrivere un [l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md), seguito da un `End Get` istruzione. Non è necessario definire i parametri per il `Get` stored procedure.  
  
2.  Inserire le istruzioni di codice per recuperare il valore della proprietà tra il `Get` e `End Get` istruzioni. Questo codice può includere altri calcoli e modifiche di dati oltre a generare e restituire il valore della proprietà.  
  
3.  Utilizzare un `Return` istruzione per restituire il valore della proprietà per il codice chiamante.  
  
 È necessario scrivere un `Get` procedura per una proprietà di lettura / scrittura e per una proprietà di sola lettura. Non è necessario definire un `Get` routine per una proprietà di sola scrittura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Per creare un Set di procedure che scrive un valore della proprietà  
  
1.  Tra le `Property` e `End Property` istruzioni, scrivere un [istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md), seguito da un `End Set` istruzione.  
  
2.  Nel `Set` istruzione, seguire la `Set` (parola chiave) con un elenco di parametri tra parentesi. Questo elenco deve includere almeno un parametro di valore per il valore passato al codice chiamante. Il nome predefinito per questo parametro è `Value`, ma è possibile utilizzare un nome diverso, se appropriato. Il parametro value deve avere gli stessi dati di tipo della proprietà stessa.  
  
3.  Inserire le istruzioni di codice per archiviare un valore nella proprietà tra il `Set` e `End Set` istruzioni. Questo codice può includere altri calcoli e modifiche di dati oltre a convalidare e memorizzare il valore della proprietà.  
  
4.  Utilizzare il parametro value per accettare il valore fornito dal codice chiamante. È possibile archiviare il valore direttamente in un'istruzione di assegnazione o utilizzarlo in un'espressione per calcolare il valore interno da archiviare.  
  
 È necessario scrivere un `Set` procedura per una proprietà di lettura / scrittura e per una proprietà di sola scrittura. Non è necessario definire un `Set` routine per una proprietà di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una proprietà di lettura/scrittura che viene archiviato un nome completo come due parti costitutive, il nome e il cognome. Quando viene letto il codice chiamante `fullName`, `Get` procedure combina le due parti costitutive e restituisce il nome completo. Quando il codice chiamante viene assegnato un nuovo nome completo, il `Set` routine tenta di suddividerla in due parti costitutive. Se non viene trovato uno spazio, memorizzato tutto come il nome.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 L'esempio seguente mostra le chiamate alle routine della proprietà di tipiche `fullName`. La prima chiamata imposta il valore della proprietà e la seconda chiamata viene recuperato.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
