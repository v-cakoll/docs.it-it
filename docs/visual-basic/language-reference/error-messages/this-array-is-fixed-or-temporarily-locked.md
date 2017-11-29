---
title: "La matrice è fissa o temporaneamente bloccata (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
