---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d384986e42ee69a0f425c1590599aa2c82bc856
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Specifica una classe può essere utilizzata solo come classe base e non è possibile creare un oggetto direttamente da esso.  
  
## <a name="remarks"></a>Note  
 Lo scopo di un *classe di base* (noto anche come un *classe astratta*) consiste nel definire le funzionalità comuni a tutte le classi derivate da esso. In questo modo le classi derivate di dover ridefinire gli elementi comuni. In alcuni casi, questa funzionalità comune non è sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità mancante. In tal caso, si desidera il codice utilizzato per creare oggetti solo dalle classi derivate. Utilizzare `MustInherit` sulla classe di base per attivare la procedura.  
  
 Un altro uso di un `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate. È possibile definire una classe di base e ne derivano tutte le classi correlate. La classe di base non è necessario fornire qualsiasi funzionalità comuni a tutte le classi derivate, ma può essere utilizzata come un filtro per assegnare valori alle variabili. Se il codice utilizzato dichiara una variabile come classe base, Visual Basic consente di assegnare solo un oggetto da una delle classi derivate a tale variabile.  
  
 .NET Framework definisce vari `MustInherit` classi, tra cui <xref:System.Array>, <xref:System.Enum>, e <xref:System.ValueType>. <xref:System.ValueType>è un esempio di una classe di base che limita una variabile. Tutti i tipi di valore derivano da <xref:System.ValueType>. Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo i tipi di valore a tale variabile.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile utilizzare `MustInherit` solo in un `Class` istruzione.  
  
-   **Modificatori combinati.** Non è possibile specificare `MustInherit` assieme `NotInheritable` nella stessa dichiarazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'ereditarietà forzata e si esegue l'override forzato. La classe di base `shape` definisce una variabile `acrossLine`. Le classi `circle` e `square` derivano da `shape`. Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché tale calcolo è diverso per ogni tipo di forma.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 È possibile dichiarare `shape1` e `shape2` sia di tipo `shape`. Tuttavia, è possibile creare un oggetto da `shape` perché dispone della funzionalità della funzione `area` ed è contrassegnato `MustInherit`.  
  
 Dal momento che vengono dichiarate come `shape`, le variabili `shape1` e `shape2` sono limitate a oggetti delle classi derivate `circle` e `square`. Visual Basic non è possibile assegnare qualsiasi altro oggetto a queste variabili, che offre un livello elevato dell'indipendenza dai tipi.  
  
## <a name="usage"></a>Utilizzo  
 Il `MustInherit` modificatore può essere utilizzato in questo contesto:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)  
 [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
