---
title: Caratteristiche di elementi dichiarati (Visual Basic)
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
ms.openlocfilehash: 26c9ec247a0b848d46df063bc7b85ceec30d81c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650894"
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
Oggetto *caratteristica* di un elemento dichiarato è un aspetto di tale elemento che influisce sulla modalità di interazione con il codice. Ogni elemento dichiarato con uno o più delle seguenti caratteristiche associate:  
  
-   *Tipo di dati* , ovvero i valori che può contenere l'elemento, e come archivia tali valori. Per ulteriori informazioni, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Durata* , ovvero il periodo di tempo di esecuzione durante il quale l'elemento è disponibile per l'utilizzo. Per ulteriori informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Ambito* , ovvero il set di tutto il codice può fare riferimento all'elemento senza qualificarne il nome. Per ulteriori informazioni, vedere [procedura: controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Livello di accesso* , ovvero l'autorizzazione per il codice all'utilizzo dell'elemento. Per ulteriori informazioni, vedere [procedura: controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Caratteristiche degli elementi  
 La tabella seguente illustra gli elementi dichiarati e le caratteristiche che si applicano a ognuna di esse.  
  
|Elemento|Tipo di dati|Durata|Ambito <sup>1</sup>|Livello di accesso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variabile|Yes|Sì|Sì|Yes|  
|Costante|Yes|No|Sì|Yes|  
|Enumerazione|Yes|No|Sì|Yes|  
|Struttura|No|No|Sì|Yes|  
|Proprietà|Yes|Sì|Sì|Yes|  
|Metodo|No|Sì|Sì|Yes|  
|Procedure (`Sub` o `Function`)|No|Sì|Sì|Yes|  
|Parametro di routine|Yes|Sì|Sì|No|  
|Valore restituito di funzione|Yes|Sì|Sì|No|  
|Operatore|Yes|No|Sì|Yes|  
|Interfaccia|No|No|Sì|Yes|  
|Classe|No|No|Sì|Yes|  
|event|No|No|Sì|Yes|  
|delegato|No|No|Sì|Yes|  
  
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
