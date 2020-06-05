---
title: La matrice è fissa o temporaneamente bloccata
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 4a86460104b6c4d9d6791e60f6f377cec0030425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363033"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>La matrice è fissa o temporaneamente bloccata (Visual Basic)
Questo errore presenta le possibili cause seguenti:  
  
- Utilizzo `ReDim` di per modificare il numero di elementi di una matrice di dimensioni fisse.  
  
- Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine. Se viene passato un elemento, la matrice viene bloccata per impedire la deallocazione della memoria per il parametro Reference all'interno della procedura.  
  
- Tentativo di assegnare un valore a una `Variant` variabile contenente una matrice, ma l'oggetto `Variant` è attualmente bloccato.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rendere la matrice originale dinamica anziché fissa dichiarando `ReDim` (se la matrice è dichiarata all'interno di una routine) o dichiarando tale matrice senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.  
  
2. Determinare se è effettivamente necessario passare l'elemento, perché è visibile all'interno di tutte le routine del modulo.  
  
3. Determinare gli elementi che bloccano `Variant` e risolvere il problema.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../programming-guide/language-features/arrays/index.md)
