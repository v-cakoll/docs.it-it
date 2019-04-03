---
title: 'Procedura: Creare una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 3e3f1168a983b2fa608cbadffba0531afef7c92b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816849"
---
# <a name="how-to-create-a-property-visual-basic"></a>Procedura: Creare una proprietà (Visual Basic)
Una proprietà definizione racchiusa tra una `Property` istruzione e una `End Property` istruzione. All'interno di questa definizione si definisce una `Get` routine, un `Set` procedure, o entrambi. Codice della proprietà si trova all'interno di queste procedure.  
  
 Il `Get` recuperando il valore della proprietà e il `Set` procedure archivia un valore. Se si vuole che la proprietà hanno accesso in lettura/scrittura, è necessario definire entrambe le procedure. Per una proprietà di sola lettura, viene definito solo `Get`, e per una proprietà di sola scrittura, si definiscono solo `Set`.  
  
### <a name="to-create-a-property"></a>Per creare una proprietà  
  
1.  All'esterno di qualsiasi proprietà o una routine, usare una [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), seguito da un `End Property` istruzione.  
  
2.  Se la proprietà accetta parametri, seguire la `Property` parola chiave con il nome della routine, quindi l'elenco di parametri tra parentesi.  
  
3.  Dopo le parentesi un `As` clausola per specificare il tipo di dati del valore della proprietà. È necessario specificare il tipo di dati anche per una proprietà di sola scrittura.  
  
4.  Aggiungere `Get` e `Set` procedure, come appropriato. Vedere le istruzioni che seguono.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Per creare una routine Get che recupera un valore della proprietà  
  
1.  Tra i `Property` e `End Property` scrivere istruzioni, una [l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md), seguito da un `End Get` istruzione. Non è necessario definire i parametri per il `Get` procedure.  
  
2.  Inserire le istruzioni di codice per recuperare il valore della proprietà tra il `Get` e `End Get` istruzioni. Questo codice può includere altri calcoli e modifiche di dati oltre a generare e restituire il valore della proprietà.  
  
3.  Usare un `Return` istruzione per restituire il valore della proprietà per il codice chiamante.  
  
 È necessario scrivere un `Get` procedure per una proprietà di lettura / scrittura e per una proprietà di sola lettura. Non è necessario definire un `Get` procedure per una proprietà di sola scrittura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Per creare un Set di procedure che scrive un valore della proprietà  
  
1.  Tra i `Property` e `End Property` scrivere istruzioni, una [istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md), seguito da un `End Set` istruzione.  
  
2.  Nel `Set` istruzione, seguire la `Set` parola chiave con un elenco di parametri tra parentesi. Questo elenco di parametri deve includere almeno un parametro di valore per il valore passato al codice chiamante. Il nome predefinito per questo parametro è `Value`, ma è possibile usare un nome diverso, se appropriato. Il parametro value deve avere gli stessi dati di tipo della proprietà stessa.  
  
3.  Inserire le istruzioni di codice per archiviare un valore nella proprietà tra il `Set` e `End Set` istruzioni. Questo codice può includere altri calcoli e modifiche di dati oltre alla convalida e archiviare il valore della proprietà.  
  
4.  Usare il parametro value per accettare il valore fornito dal codice chiamante. È possibile archiviare questo valore direttamente in un'istruzione di assegnazione, o usarla in un'espressione per calcolare il valore interno da archiviare.  
  
 È necessario scrivere un `Set` procedure per una proprietà di lettura / scrittura e per una proprietà di sola scrittura. Non è necessario definire un `Set` procedure per una proprietà di sola lettura.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una proprietà di lettura/scrittura che archivia un nome completo come due parti costitutive, il nome e cognome. Quando legge il codice chiamante `fullName`, il `Get` procedure combina le due parti costitutive e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, il `Set` routine tenta di suddividere l'operazione in due parti costitutive. Se non viene trovato uno spazio, li archivia tutti come il nome.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 L'esempio seguente illustra tipici chiamate alle routine della proprietà di `fullName`. La prima chiamata imposta il valore della proprietà e la seconda chiamata li recupera.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
