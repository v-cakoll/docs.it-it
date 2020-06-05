---
title: Differenze tra proprietà e variabili
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: 162bd71eaebdf55f6be89e0c5dce7acc1b975d79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403304"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Differenze tra proprietà e variabili in Visual Basic
Le variabili e le proprietà rappresentano entrambi i valori a cui è possibile accedere. Tuttavia, esistono differenze nell'archiviazione e nell'implementazione.  
  
## <a name="variables"></a>variables  
 Una *variabile* corrisponde direttamente a una posizione di memoria. Si definisce una variabile con un'unica istruzione di dichiarazione. Una variabile può essere una *variabile locale*, definita all'interno di una routine e disponibile solo all'interno di tale procedura, oppure può essere una *variabile membro*, definita in un modulo, una classe o una struttura, ma non all'interno di alcuna routine. Una variabile membro viene anche chiamata *campo*.  
  
## <a name="properties"></a>Proprietà  
 Una *Proprietà* è un elemento dati definito in un modulo, una classe o una struttura. Si definisce una proprietà con un blocco di codice tra `Property` le `End Property` istruzioni e. Il blocco di codice contiene una `Get` routine, una `Set` routine o entrambe. Queste procedure sono denominate *routine di proprietà* o *funzioni di accesso alle proprietà*. Oltre a recuperare o archiviare il valore della proprietà, possono anche eseguire azioni personalizzate, ad esempio l'aggiornamento di un contatore di accesso.  
  
## <a name="differences"></a>Differenze  
 Nella tabella seguente vengono illustrate alcune differenze importanti tra le variabili e le proprietà.  
  
|Punto di differenza|Variabile|Proprietà|  
|-------------------------|--------------|--------------|  
|Dichiarazione|Singola istruzione di dichiarazione|Serie di istruzioni in un blocco di codice|  
|Implementazione|Posizione di archiviazione singola|Codice eseguibile (routine Property)|  
|Archiviazione|Associato direttamente al valore della variabile|In genere l'archiviazione interna non è disponibile all'esterno della classe o del modulo contenitore della proprietà<br /><br /> Il valore della proprietà può essere o meno esistere come elemento archiviato <sup>1</sup>|  
|Codice eseguibile|nessuno|Deve avere almeno una procedura|  
|Accesso in lettura e scrittura|Lettura/scrittura o sola lettura|Lettura/scrittura, di sola lettura o di sola scrittura|  
|Azioni personalizzate (oltre all'accettazione o alla restituzione di un valore)|Non consentita|Può essere eseguita come parte dell'impostazione o del recupero del valore della proprietà|  
  
 <sup>1</sup> diversamente da una variabile, il valore di una proprietà potrebbe non corrispondere direttamente a un singolo elemento di archiviazione. Lo spazio di archiviazione può essere suddiviso in parti per comodità o sicurezza oppure il valore può essere archiviato in formato crittografato. In questi casi `Get` , la procedura può assemblare le parti o decrittografare il valore archiviato e la procedura esegue la `Set` crittografia del nuovo valore o lo suddivide nell'archivio costituente. Un valore di proprietà può essere effimero, ad esempio l'ora del giorno, nel qual caso la `Get` procedura la calcolerà in tempo reale ogni volta che si accede alla proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)
- [Procedura: creare una proprietà](./how-to-create-a-property.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)
- [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
