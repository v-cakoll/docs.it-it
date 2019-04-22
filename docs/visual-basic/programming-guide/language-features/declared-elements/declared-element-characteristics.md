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
ms.openlocfilehash: 98f6a7738a462e9f36abdc0380cb1fe8d488fb9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821296"
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
Oggetto *caratteristica* di un elemento dichiarato è un aspetto di tale elemento che influisce sulla modalità di interazione con il codice. Ogni elemento dichiarato con uno o più delle caratteristiche seguenti associate:  
  
-   *Tipo di dati* , ovvero i valori che può contenere l'elemento e modalità di archiviazione di tali valori. Per altre informazioni, vedere [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
-   *Durata* , ovvero il periodo di tempo di esecuzione durante il quale l'elemento è disponibile per l'uso. Per altre informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Ambito* , ovvero il set di tutto il codice che può fare riferimento all'elemento senza il nome completo. Per altre informazioni, vedere [Procedura: Controllare l'ambito di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Livello di accesso* , ovvero l'autorizzazione per il codice all'utilizzo dell'elemento. Per altre informazioni, vedere [Procedura: Controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Caratteristiche degli elementi  
 La tabella seguente illustra gli elementi dichiarati e le caratteristiche che si applicano a ognuno di essi.  
  
|Elemento|Tipo di dati|Durata|Scope <sup>1</sup>|Livello di accesso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variabile|Yes|Yes|Yes|Yes|  
|Costante|Yes|No|Yes|Yes|  
|Enumerazione|Yes|No|Yes|Yes|  
|Struttura|No|No|Yes|Yes|  
|Proprietà|Yes|Yes|Yes|Yes|  
|Metodo|No|Yes|Yes|Yes|  
|Procedure (`Sub` o `Function`)|No|Yes|Yes|Yes|  
|Parametro di routine|Yes|Yes|Yes|No|  
|Restituito dalla funzione|Yes|Yes|Yes|No|  
|Operatore|Yes|No|Yes|Yes|  
|Interfaccia|No|No|Yes|Yes|  
|Classe|No|No|Yes|Yes|  
|event|No|No|Yes|Yes|  
|delegato|No|No|Yes|Yes|  
  
 <sup>1</sup> ambito è talvolta detta *visibilità*.  
  
## <a name="see-also"></a>Vedere anche

- [Elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
