---
title: 'Procedura: creare una proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: fa220998d12206e620c242b9b39df3dc1b639d29
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388258"
---
# <a name="how-to-create-a-property-visual-basic"></a>Procedura: creare una proprietà (Visual Basic)
Racchiudere una definizione di proprietà tra un' `Property` istruzione e un' `End Property` istruzione. All'interno di questa definizione si definisce una `Get` routine, una `Set` routine o entrambe. Tutto il codice della proprietà si trova all'interno di queste procedure.  
  
 La `Get` stored procedure recupera il valore della proprietà e `Set` Archivia un valore. Se si desidera che la proprietà disponga di accesso in lettura/scrittura, è necessario definire entrambe le routine. Per una proprietà di sola lettura, si definiscono solo `Get` e per una proprietà di sola scrittura è sufficiente definire `Set` .  
  
### <a name="to-create-a-property"></a>Per creare una proprietà  
  
1. All'esterno di qualsiasi proprietà o routine, utilizzare un' [istruzione Property](../../../language-reference/statements/property-statement.md), seguita da un' `End Property` istruzione.  
  
2. Se la proprietà accetta parametri, seguire la `Property` parola chiave con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.  
  
3. Seguire le parentesi con una `As` clausola per specificare il tipo di dati del valore della proprietà. È necessario specificare il tipo di dati anche per una proprietà di sola scrittura.  
  
4. Aggiungere `Get` `Set` le procedure e, a seconda delle esigenze. Vedere le istruzioni seguenti.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Per creare una procedura Get che recupera un valore della proprietà  
  
1. Tra le `Property` `End Property` istruzioni e, scrivere un' [istruzione Get](../../../language-reference/statements/get-statement.md), seguita da un' `End Get` istruzione. Non è necessario definire parametri per la `Get` procedura.  
  
2. Inserire le istruzioni del codice per recuperare il valore della proprietà tra `Get` le `End Get` istruzioni e. Questo codice può includere altri calcoli e modifiche dei dati, oltre a generare e restituire il valore della proprietà.  
  
3. Utilizzare un' `Return` istruzione per restituire il valore della proprietà al codice chiamante.  
  
 È necessario scrivere una `Get` routine per una proprietà di lettura/scrittura e per una proprietà di sola lettura. Non è necessario definire una `Get` routine per una proprietà di sola scrittura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Per creare una routine set che scrive il valore di una proprietà  
  
1. Tra le `Property` `End Property` istruzioni e, scrivere un' [istruzione set](../../../language-reference/statements/set-statement.md), seguita da un' `End Set` istruzione.  
  
2. Nell' `Set` istruzione seguire la `Set` parola chiave con un elenco di parametri racchiusi tra parentesi. Questo elenco di parametri deve includere almeno un parametro di valore per il valore passato dal codice chiamante. Il nome predefinito per questo parametro di valore è `Value` , ma è possibile usare un nome diverso, se appropriato. Il parametro value deve avere lo stesso tipo di dati della proprietà stessa.  
  
3. Inserire le istruzioni di codice per archiviare un valore nella proprietà tra le `Set` `End Set` istruzioni e. Questo codice può includere altri calcoli e modifiche dei dati, oltre a convalidare e archiviare il valore della proprietà.  
  
4. Usare il parametro value per accettare il valore fornito dal codice chiamante. È possibile archiviare questo valore direttamente in un'istruzione di assegnazione oppure utilizzarlo in un'espressione per calcolare il valore interno da archiviare.  
  
 È necessario scrivere una `Set` routine per una proprietà di lettura/scrittura e per una proprietà di sola scrittura. Non è necessario definire una `Set` routine per una proprietà di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una proprietà di lettura/scrittura che archivia un nome completo come due nomi costitutivi, il primo nome e il cognome. Quando il codice chiamante viene letto `fullName` , la `Get` procedura combina i due nomi costitutivi e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, la `Set` routine tenta di suddividerla in due nomi costitutivi. Se non trova uno spazio, lo archivia come nome.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine di proprietà di `fullName` . La prima chiamata imposta il valore della proprietà e la seconda chiamata la Recupera.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
