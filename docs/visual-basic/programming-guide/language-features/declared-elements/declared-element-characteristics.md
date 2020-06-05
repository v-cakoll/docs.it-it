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
ms.openlocfilehash: 9d1e327c25689bed1405ea9a627da6232abb707b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392948"
---
# <a name="declared-element-characteristics-visual-basic"></a>Caratteristiche di elementi dichiarati (Visual Basic)
Una *caratteristica* di un elemento dichiarato è un aspetto di tale elemento che influiscono sul modo in cui il codice può interagire con esso. A ogni elemento dichiarato sono associate una o più delle seguenti caratteristiche:  
  
- *Tipo di dati* : i valori che l'elemento può memorizzare e il modo in cui archivia tali valori. Per altre informazioni, vedere [Tipi di dati](../../../language-reference/data-types/index.md).  
  
- *Lifetime* : periodo di tempo di esecuzione durante il quale l'elemento è disponibile per l'utilizzo. Per ulteriori informazioni, vedere [Lifetime in Visual Basic](lifetime.md).  
  
- *Scope (ambito* ): set di tutto il codice che può fare riferimento all'elemento senza qualificare il nome. Per altre informazioni, vedere [procedura: controllare l'ambito di una variabile](how-to-control-the-scope-of-a-variable.md).  
  
- *Livello di accesso* : autorizzazione per il codice a usare l'elemento. Per altre informazioni, vedere [procedura: controllare la disponibilità di una variabile](how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Caratteristiche degli elementi  
 La tabella seguente Mostra gli elementi dichiarati e le caratteristiche che si applicano a ciascuna di esse.  
  
|Elemento|Tipo di dati|Durata|Ambito <sup>1</sup>|Livello di accesso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variabile|Sì|Sì|Sì|Sì|  
|Costante|Sì|No|Sì|Sì|  
|Enumerazione|Sì|No|Sì|Sì|  
|Struttura|No|No|Sì|Sì|  
|Proprietà|Sì|Sì|Sì|Sì|  
|Metodo|No|Sì|Sì|Sì|  
|Routine ( `Sub` o `Function` )|No|Sì|Sì|Sì|  
|Parametro di routine|Sì|Sì|Sì|No|  
|Funzione restituita|Sì|Sì|Sì|No|  
|Operatore|Sì|No|Sì|Sì|  
|Interfaccia|No|No|Sì|Sì|  
|Class|No|No|Sì|Sì|  
|Event|No|No|Sì|Sì|  
|Delegato|No|No|Sì|Sì|  
  
 <sup>1</sup> l'ambito viene talvolta definito *visibilità*.  
  
## <a name="see-also"></a>Vedere anche

- [Elementi dichiarati](index.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Durata in Visual Basic](lifetime.md)
- [Ambito in Visual Basic](scope.md)
- [Livelli di accesso in Visual Basic](access-levels.md)
- [Tipi di dati](../data-types/index.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
