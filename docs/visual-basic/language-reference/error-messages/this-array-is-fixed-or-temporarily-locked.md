---
title: La matrice è fissa o temporaneamente bloccata (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c7b5372b6046e25aad87131ba141cb71c580e12c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625948"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>La matrice è fissa o temporaneamente bloccata (Visual Basic)
Questo errore sono le seguenti cause possibili:  
  
- Usando `ReDim` per modificare il numero di elementi di una matrice di dimensioni fisse.  
  
- Ridimensionamento di una matrice dinamica a livello di modulo, in cui un elemento è stato passato come argomento a una routine. Se viene passato un elemento, la matrice è bloccata per evitare la deallocazione di memoria per il parametro di riferimento all'interno della routine.  
  
- Tentativo di assegnare un valore a un `Variant` variabile che contiene una matrice, ma il `Variant` è attualmente bloccato.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rendere la matrice originale dinamica anziché fissa dichiarandolo con `ReDim` (se la matrice viene dichiarata all'interno di una procedura), oppure dichiarandolo senza specificare il numero di elementi (se la matrice viene dichiarata a livello di modulo.  
  
2. Determinare se è realmente necessario passare l'elemento, dato che è visibile all'interno di tutte le procedure nel modulo.  
  
3. Determinare quali blocchi di `Variant` e porvi rimedio.  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
