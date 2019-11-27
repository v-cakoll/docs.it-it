---
title: 'Procedura: creare una proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: ee5a9f687765ce064eb3c3f84218ed36eb916d9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349707"
---
# <a name="how-to-create-a-property-visual-basic"></a>Procedura: creare una proprietà (Visual Basic)
È possibile racchiudere una definizione di proprietà tra un'istruzione `Property` e un'istruzione `End Property`. All'interno di questa definizione è possibile definire una procedura di `Get`, una `Set` o entrambi. Tutto il codice della proprietà si trova all'interno di queste procedure.  
  
 La procedura `Get` Recupera il valore della proprietà e la stored procedure `Set` archivia un valore. Se si desidera che la proprietà disponga di accesso in lettura/scrittura, è necessario definire entrambe le routine. Per una proprietà di sola lettura, si definiscono solo `Get`e per una proprietà di sola scrittura è necessario definire solo `Set`.  
  
### <a name="to-create-a-property"></a>Per creare una proprietà  
  
1. All'esterno di qualsiasi proprietà o routine, utilizzare un' [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md), seguita da un'istruzione `End Property`.  
  
2. Se la proprietà accetta parametri, seguire la parola chiave `Property` con il nome della stored procedure, quindi l'elenco di parametri tra parentesi.  
  
3. Seguire le parentesi con una clausola `As` per specificare il tipo di dati del valore della proprietà. È necessario specificare il tipo di dati anche per una proprietà di sola scrittura.  
  
4. Aggiungere `Get` e `Set` procedure, a seconda delle esigenze. Vedere le istruzioni seguenti.  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a>Per creare una procedura Get che recupera un valore della proprietà  
  
1. Tra le istruzioni `Property` e `End Property`, scrivere un' [istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md), seguita da un'istruzione `End Get`. Non è necessario definire parametri per la procedura `Get`.  
  
2. Inserire le istruzioni del codice per recuperare il valore della proprietà tra le istruzioni `Get` e `End Get`. Questo codice può includere altri calcoli e modifiche dei dati, oltre a generare e restituire il valore della proprietà.  
  
3. Utilizzare un'istruzione `Return` per restituire il valore della proprietà al codice chiamante.  
  
 È necessario scrivere una procedura `Get` per una proprietà di lettura/scrittura e per una proprietà di sola lettura. Non è necessario definire una procedura di `Get` per una proprietà di sola scrittura.  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a>Per creare una routine set che scrive il valore di una proprietà  
  
1. Tra le istruzioni `Property` e `End Property`, scrivere un' [istruzione set](../../../../visual-basic/language-reference/statements/set-statement.md), seguita da un'istruzione `End Set`.  
  
2. Nell'istruzione `Set` seguire la parola chiave `Set` con un elenco di parametri racchiusi tra parentesi. Questo elenco di parametri deve includere almeno un parametro di valore per il valore passato dal codice chiamante. Il nome predefinito per questo parametro di valore è `Value`, ma è possibile usare un nome diverso, se appropriato. Il parametro value deve avere lo stesso tipo di dati della proprietà stessa.  
  
3. Inserire le istruzioni di codice per archiviare un valore nella proprietà tra le istruzioni `Set` e `End Set`. Questo codice può includere altri calcoli e modifiche dei dati, oltre a convalidare e archiviare il valore della proprietà.  
  
4. Usare il parametro value per accettare il valore fornito dal codice chiamante. È possibile archiviare questo valore direttamente in un'istruzione di assegnazione oppure utilizzarlo in un'espressione per calcolare il valore interno da archiviare.  
  
 È necessario scrivere una procedura `Set` per una proprietà di lettura/scrittura e per una proprietà di sola scrittura. Non è necessario definire una procedura di `Set` per una proprietà di sola lettura.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una proprietà di lettura/scrittura che archivia un nome completo come due nomi costitutivi, il primo nome e il cognome. Quando il codice chiamante legge `fullName`, la procedura `Get` combina i due nomi costitutivi e restituisce il nome completo. Quando il codice chiamante assegna un nuovo nome completo, la `Set` routine tenta di suddividerla in due nomi costitutivi. Se non trova uno spazio, lo archivia come nome.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine della proprietà di `fullName`. La prima chiamata imposta il valore della proprietà e la seconda chiamata la Recupera.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
