---
title: "Differenze tra proprietà e variabili in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb30972e2b49a7005749f57c0223b9fa493cde52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Differenze tra proprietà e variabili in Visual Basic
Le variabili e le proprietà rappresentano valori che è possibile accedere. Tuttavia, esistono differenze nell'archiviazione e di implementazione.  
  
## <a name="variables"></a>Variabili  
 Oggetto *variabile* corrisponde direttamente a una posizione di memoria. Definire una variabile con una singola istruzione di dichiarazione. Una variabile può essere un *variabile locale*, definito all'interno di una stored procedure e disponibile solo in questa procedura, o può essere un *variabile membro*, definita in un modulo, classe o struttura ma non all'interno di uno stored procedure. Una variabile membro viene inoltre chiamata un *campo*.  
  
## <a name="properties"></a>Proprietà  
 Oggetto *proprietà* è un elemento di dati definito in un modulo, classe o struttura. Si definisce una proprietà con un blocco di codice tra le `Property` e `End Property` istruzioni. Il blocco di codice contiene un `Get` procedure, un `Set` procedure o entrambi. Queste procedure sono dette *le routine della proprietà* o *accesso della proprietà*. Oltre a recuperare o archiviare il valore della proprietà, nonché eseguire azioni personalizzate, ad esempio l'aggiornamento di un contatore di accesso.  
  
## <a name="differences"></a>Differenze  
 La tabella seguente illustra alcune importanti differenze tra variabili e proprietà.  
  
|Punto di differenza|Variabile|Proprietà|  
|-------------------------|--------------|--------------|  
|Dichiarazione|Singola istruzione di dichiarazione|Serie di istruzioni in un blocco di codice|  
|Implementazione|Percorso di archiviazione singolo|Codice eseguibile (routine delle proprietà)|  
|Archiviazione|Direttamente associati con il valore della variabile|In genere la memoria interna non è disponibile all'esterno di classe o il modulo contenente la proprietà<br /><br /> Valore della proprietà potrebbe o meno esistere come elemento memorizzato <sup>1</sup>|  
|Codice eseguibile|None|Deve avere almeno una delle procedure|  
|Accesso in lettura e scrittura|Lettura/scrittura o sola lettura|Lettura/scrittura, sola lettura, lettura o scrittura|  
|Azioni personalizzate (oltre che accetta o restituendo valore)|Non è possibile|Possono essere eseguiti come parte dell'impostazione o il recupero del valore di proprietà|  
  
 <sup>1</sup> a differenza di una variabile, il valore di una proprietà potrebbe non corrispondere direttamente a un singolo elemento di archiviazione. Lo spazio di archiviazione potrebbe essere suddivisa in parti per motivi di praticità o protezione o il valore potrebbe essere archiviato in formato crittografato. In questi casi il `Get` routine assemblare le parti o decrittografare il valore archiviato e `Set` procedura consente di crittografare il nuovo valore o suddividerlo nello spazio di archiviazione che lo costituiscono. Valore della proprietà potrebbe essere temporaneo, come l'ora del giorno, nel qual caso il `Get` procedura sarebbe calcolarla in tempo reale ogni volta che si accede alla proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
