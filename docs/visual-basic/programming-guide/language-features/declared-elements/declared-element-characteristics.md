---
title: Caratteristiche di elementi dichiarati
ms.date: 07/20/2015
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
ms.openlocfilehash: 4e03cd28fed5e0ae109337739251c11a0ff3424a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331632"
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
Una *caratteristica* di un elemento dichiarato è un aspetto di tale elemento che influiscono sul modo in cui il codice può interagire con esso. A ogni elemento dichiarato sono associate una o più delle seguenti caratteristiche:  
  
- *Tipo di dati* : i valori che l'elemento può memorizzare e il modo in cui archivia tali valori. Per altre informazioni, vedere [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
- *Lifetime* : periodo di tempo di esecuzione durante il quale l'elemento è disponibile per l'utilizzo. Per ulteriori informazioni, vedere [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- *Scope (ambito* ): set di tutto il codice che può fare riferimento all'elemento senza qualificare il nome. Per altre informazioni, vedere [procedura: controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
- *Livello di accesso* : autorizzazione per il codice a usare l'elemento. Per altre informazioni, vedere [procedura: controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Caratteristiche degli elementi  
 La tabella seguente Mostra gli elementi dichiarati e le caratteristiche che si applicano a ciascuna di esse.  
  
|Elemento|Tipo di dati|Durata|Ambito <sup>1</sup>|Livello di accesso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Sì|Sì|Sì|Sì|  
|Costante|Sì|No|Sì|Sì|  
|Enumerazione|Sì|No|Sì|Sì|  
|Struttura|No|No|Sì|Sì|  
|Proprietà|Sì|Sì|Sì|Sì|  
|Metodo|No|Sì|Sì|Sì|  
|Routine (`Sub` o `Function`)|No|Sì|Sì|Sì|  
|Parametro di routine|Sì|Sì|Sì|No|  
|Funzione restituita|Sì|Sì|Sì|No|  
|Operatore|Sì|No|Sì|Sì|  
|Interfaccia|No|No|Sì|Sì|  
|Classe|No|No|Sì|Sì|  
|Evento|No|No|Sì|Sì|  
|Delegato|No|No|Sì|Sì|  
  
 <sup>1</sup> l'ambito viene talvolta definito *visibilità*.  
  
## <a name="see-also"></a>Vedere anche

- [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
