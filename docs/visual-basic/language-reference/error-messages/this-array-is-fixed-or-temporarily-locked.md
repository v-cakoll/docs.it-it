---
title: La matrice è fissa o temporaneamente bloccata
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350781"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>La matrice è fissa o temporaneamente bloccata (Visual Basic)
Questo errore presenta le possibili cause seguenti:  
  
- Utilizzo di `ReDim` per modificare il numero di elementi di una matrice di dimensioni fisse.  
  
- Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine. Se viene passato un elemento, la matrice viene bloccata per impedire la deallocazione della memoria per il parametro Reference all'interno della procedura.  
  
- Tentativo di assegnare un valore a una variabile `Variant` contenente una matrice, ma il `Variant` è attualmente bloccato.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rendere dinamica la matrice originale anziché fissa dichiarando l'oggetto con `ReDim` (se la matrice è dichiarata all'interno di una routine) o dichiarando il numero di elementi (se la matrice viene dichiarata a livello di modulo.  
  
2. Determinare se è effettivamente necessario passare l'elemento, perché è visibile all'interno di tutte le routine del modulo.  
  
3. Determinare gli elementi che bloccano il `Variant` e risolvere il problema.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
