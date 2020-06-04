---
title: MustInherit
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
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396207"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Specifica che una classe può essere utilizzata solo come classe base e che non è possibile creare un oggetto direttamente da tale classe.  
  
## <a name="remarks"></a>Commenti  
 Lo scopo di una *classe di base* (nota anche come *classe astratta*) consiste nel definire la funzionalità comune a tutte le classi derivate. Questo consente di salvare le classi derivate dalla necessità di ridefinire gli elementi comuni. In alcuni casi, questa funzionalità comune non è sufficientemente completa per creare un oggetto utilizzabile e ogni classe derivata definisce la funzionalità mancante. In tal caso, si desidera che il codice consumer crei oggetti solo dalle classi derivate. Usare `MustInherit` nella classe di base per applicare questa operazione.  
  
 Un altro uso di una `MustInherit` classe consiste nel limitare una variabile a un set di classi correlate. È possibile definire una classe di base e derivare tutte le classi correlate. La classe base non deve fornire funzionalità comuni a tutte le classi derivate, ma può fungere da filtro per l'assegnazione di valori alle variabili. Se il codice consumer dichiara una variabile come classe di base, Visual Basic consente di assegnare a tale variabile solo un oggetto da una delle classi derivate.  
  
 Il .NET Framework definisce diverse `MustInherit` classi, tra cui <xref:System.Array> , <xref:System.Enum> e <xref:System.ValueType> . <xref:System.ValueType>è un esempio di una classe di base che limita una variabile. Tutti i tipi di valore derivano da <xref:System.ValueType> . Se si dichiara una variabile come <xref:System.ValueType> , è possibile assegnare solo tipi valore a tale variabile.  
  
## <a name="rules"></a>Regole  
  
- **Contesto della dichiarazione. ** È possibile utilizzare `MustInherit` solo in un' `Class` istruzione.  
  
- **Modificatori combinati.** Non è possibile specificare `MustInherit` insieme `NotInheritable` a nella stessa dichiarazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'ereditarietà forzata e l'override forzato. La classe base `shape` definisce una variabile `acrossLine` . Le classi `circle` e `square` derivano da `shape` . Ereditano la definizione di `acrossLine` , ma devono definire la funzione `area` perché il calcolo è diverso per ogni tipo di forma.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 È possibile dichiarare `shape1` e `shape2` per essere di tipo `shape` . Tuttavia, non è possibile creare un oggetto da `shape` perché manca la funzionalità della funzione `area` ed è contrassegnato `MustInherit` .  
  
 Poiché sono dichiarati come `shape` , le variabili `shape1` e `shape2` sono limitate agli oggetti delle classi derivate `circle` e `square` . Visual Basic non consente di assegnare altri oggetti a queste variabili, che offre un livello elevato di indipendenza dai tipi.  
  
## <a name="usage"></a>Uso  
 Il `MustInherit` modificatore può essere usato in questo contesto:  
  
 [Istruzione Class](../statements/class-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Inherits Statement](../statements/inherits-statement.md)
- [NotInheritable](notinheritable.md)
- [Parole chiave](../keywords/index.md)
- [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
