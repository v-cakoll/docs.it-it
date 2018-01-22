---
title: "&#39; ReDim &#39; può modificare solo la dimensione più a destra"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a>&#39; ReDim &#39; può modificare solo la dimensione più a destra
Un'istruzione `ReDim` ha tentato di usare la parola chiave `Preserve` per modificare una dimensione di una matrice che non è l'ultima dimensione. Quando si usa `Preserve`, si può ridimensionare solo l'ultima dimensione di una matrice. Per tutte le altre, è necessario specificare le stesse dimensioni di una matrice esistente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere la parola chiave `Preserve` .  
  
## <a name="see-also"></a>Vedere anche  
 [Matrici in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Dimensioni di matrice in Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [Istruzione ReDim](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Istruzione Dim](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Preserve - eliminazione](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
