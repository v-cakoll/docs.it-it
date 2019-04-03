---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816564"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Specifica una classe può essere utilizzata solo come classe di base e non è possibile creare un oggetto direttamente da esso.  
  
## <a name="remarks"></a>Note  
 Lo scopo di un *classe di base* (noto anche come un' *classe astratta*) consiste nel definire funzionalità comuni a tutte le classi da esso derivate. In questo modo le classi derivate di dover ridefinire gli elementi comuni. In alcuni casi, queste funzionalità comuni non sono sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità manca. In tal caso, è necessario il codice utilizzato per creare oggetti solo dalle classi derivate. Si utilizza `MustInherit` nella classe di base per applicare questo comportamento.  
  
 Un altro uso di un `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate. È possibile definire una classe di base e ne derivano tutte le classi correlate. La classe di base non è necessario fornire qualsiasi funzionalità comuni a tutte le classi derivate, ma possono fungere da un filtro per assegnare valori alle variabili. Se il codice consumer dichiara una variabile come la classe di base, Visual Basic consente di assegnare solo un oggetto da una delle classi derivate a tale variabile.  
  
 .NET Framework definisce vari `MustInherit` classi, tra di essi <xref:System.Array>, <xref:System.Enum>, e <xref:System.ValueType>. <xref:System.ValueType> è un esempio di una classe di base che limita una variabile. Tutti i tipi valore derivano da <xref:System.ValueType>. Se si dichiara una variabile come <xref:System.ValueType>, è possibile assegnare solo i tipi di valore alla variabile.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** È possibile usare `MustInherit` solo in un `Class` istruzione.  
  
-   **Modificatori combinati.** Non è possibile specificare `MustInherit` insieme a `NotInheritable` nella stessa dichiarazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'ereditarietà forzata e forzato viene sottoposto a override. La classe di base `shape` definisce una variabile `acrossLine`. Le classi `circle` e `square` derivano da `shape`. Ereditano la definizione di `acrossLine`, ma devono definire la funzione `area` perché questo calcolo è diverso per ogni tipo di forma.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 È possibile dichiarare `shape1` e `shape2` di tipo `shape`. Tuttavia, è possibile creare un oggetto dal `shape` perché manca la funzionalità della funzione `area` ed è contrassegnato `MustInherit`.  
  
 Poiché sono stati dichiarati come `shape`, le variabili `shape1` e `shape2` sono limitate a oggetti delle classi derivate `circle` e `square`. Visual Basic non consente di assegnare qualsiasi altro oggetto a queste variabili, che ti offre un elevato livello di indipendenza dai tipi.  
  
## <a name="usage"></a>Utilizzo  
 Il `MustInherit` modificatore può essere usato in questo contesto:  
  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
