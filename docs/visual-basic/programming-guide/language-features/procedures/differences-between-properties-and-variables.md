---
title: Differenze tra proprietà e variabili in Visual Basic
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
ms.openlocfilehash: de4800e23519c2cc1c8b2b219287b9fa018b9bbf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842902"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Differenze tra proprietà e variabili in Visual Basic
Le variabili e le proprietà rappresentano valori che è possibile accedere. Tuttavia, esistono differenze di archiviazione e implementazione.  
  
## <a name="variables"></a>Variabili  
 Oggetto *variabile* corrisponde direttamente a una posizione di memoria. Si definisce una variabile con una singola istruzione di dichiarazione. Una variabile può essere un *variabile locale*, definito all'interno di una procedura e disponibile solo all'interno di tale routine o può essere una *variabile membro*, definito in un modulo, classe o struttura, ma non all'interno di uno procedura. Una variabile membro viene chiamata anche un *campo*.  
  
## <a name="properties"></a>Proprietà  
 Oggetto *proprietà* è un elemento di dati definito in un modulo, classe o struttura. Si definisce una proprietà con un blocco di codice tra il `Property` e `End Property` istruzioni. Il blocco di codice contiene un `Get` routine, un `Set` procedure, o entrambi. Queste procedure sono dette *routine property* oppure *funzioni di accesso proprietà*. Oltre a recuperare o archiviare il valore della proprietà, è anche possibile eseguire azioni personalizzate, ad esempio l'aggiornamento di un contatore di accesso.  
  
## <a name="differences"></a>Differenze  
 Nella tabella seguente vengono illustrate alcune differenze importanti tra variabili e proprietà.  
  
|Punto di differenza|Variabile|Proprietà|  
|-------------------------|--------------|--------------|  
|Dichiarazione|Singola istruzione di dichiarazione|Serie di istruzioni in un blocco di codice|  
|Implementazione|Percorso di archiviazione singolo|Codice eseguibile (routine delle proprietà)|  
|Archiviazione|Associati direttamente con il valore della variabile|In genere la memoria interna non disponibile di fuori della proprietà classe o modulo<br /><br /> Valore della proprietà potrebbe o meno esistere come elemento archiviato <sup>1</sup>|  
|Codice eseguibile|nessuno|Deve avere almeno una routine|  
|Accesso in lettura e scrittura|Lettura/scrittura o sola lettura|Lettura/scrittura, sola lettura, lettura o scrittura|  
|Azioni personalizzate (oltre all'accettazione o la restituzione di valore)|Non è possibile|Può essere eseguita come parte dell'impostazione o recupero di valore della proprietà|  
  
 <sup>1</sup> a differenza di una variabile, il valore di una proprietà potrebbe non corrispondere direttamente a un singolo elemento di spazio di archiviazione. Lo spazio di archiviazione è possibile suddividere in parti per comodità o della sicurezza o il valore potrebbe essere archiviato in formato crittografato. In questi casi il `Get` routine assemblare le parti o decrittografare il valore archiviato e `Set` routine crittografare il nuovo valore o suddividerlo in risorsa di archiviazione che lo costituiscono. Valore della proprietà potrebbe essere temporaneo, come l'ora del giorno, nel qual caso il `Get` procedure sarebbe calcolarla in tempo reale ogni volta che si accede alla proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
