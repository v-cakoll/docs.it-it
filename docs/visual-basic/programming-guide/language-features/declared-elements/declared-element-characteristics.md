---
title: Caratteristiche di elementi dichiarati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26ee27d3a1d085c6ab45ae850dbdac700aa208a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
Oggetto *caratteristica* di un elemento dichiarato è un aspetto di tale elemento che influisce sulla modalità di interazione con il codice. Ogni elemento dichiarato con uno o più delle seguenti caratteristiche associate:  
  
-   *Tipo di dati* : i valori che può contenere l'elemento e la modalità di archiviazione. Per ulteriori informazioni, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Durata* , ovvero il periodo di tempo di esecuzione durante il quale l'elemento è disponibile per l'utilizzo. Per ulteriori informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Ambito* , ovvero il set di tutto il codice può fare riferimento all'elemento senza qualificarne il nome. Per ulteriori informazioni, vedere [procedura: controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Livello di accesso* , ovvero l'autorizzazione per il codice all'utilizzo dell'elemento. Per ulteriori informazioni, vedere [procedura: controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Caratteristiche degli elementi  
 La tabella seguente illustra gli elementi dichiarati e le caratteristiche che si applicano a ognuna di esse.  
  
|Elemento|Tipo di dati|Durata|Ambito <sup>1</sup>|Livello di accesso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variabile|Sì|Sì|Sì|Sì|  
|Costante|Sì|No|Sì|Sì|  
|Enumerazione|Sì|No|Sì|Sì|  
|Struttura|No|No|Sì|Sì|  
|Proprietà|Sì|Sì|Sì|Sì|  
|Metodo|No|Sì|Sì|Sì|  
|Procedure (`Sub` o `Function`)|No|Sì|Sì|Sì|  
|Parametro di routine|Sì|Sì|Sì|No|  
|Valore restituito di funzione|Sì|Sì|Sì|No|  
|Operatore|Sì|No|Sì|Sì|  
|Interfaccia|No|No|Sì|Sì|  
|Classe|No|No|Sì|Sì|  
|Evento|No|No|Sì|Sì|  
|Delegato|No|No|Sì|Sì|  
  
 <sup>1</sup> ambito è talvolta detta *visibilità*.  
  
## <a name="see-also"></a>Vedere anche  
 [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
