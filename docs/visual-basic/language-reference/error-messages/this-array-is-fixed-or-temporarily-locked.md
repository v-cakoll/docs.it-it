---
title: La matrice è fissa o temporaneamente bloccata (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593564"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>La matrice è fissa o temporaneamente bloccata (Visual Basic)
Questo errore sono le seguenti cause possibili:  
  
-   Utilizzando `ReDim` per modificare il numero di elementi di una matrice di dimensioni fisse.  
  
-   Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine. Se un elemento viene passato, la matrice è bloccata per impedire la deallocazione di memoria per il parametro di riferimento all'interno della routine.  
  
-   Il tentativo di assegnare un valore a un `Variant` variabile che contiene una matrice, ma la `Variant` è attualmente bloccato.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Rendere la matrice originale dinamica anziché dichiarandola con `ReDim` (se è dichiarata all'interno di una stored procedure), sia che venga dichiarata senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.  
  
2.  Determinare se sia necessario per passare l'elemento, dato che è visibile all'interno di tutte le procedure nel modulo.  
  
3.  Stabilire cosa blocca il `Variant` e correzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Array](../../../visual-basic/programming-guide/language-features/arrays/index.md)
