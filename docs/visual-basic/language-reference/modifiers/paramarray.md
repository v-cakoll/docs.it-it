---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: be8ddb7f9ba08535d12890d1c5c82a9b7b485f3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato. `ParamArray` può essere utilizzato solo sull'ultimo parametro di un elenco di parametri.  
  
## <a name="remarks"></a>Note  
 `ParamArray` Consente di passare un numero arbitrario di argomenti per la procedura. Oggetto `ParamArray` parametro sempre è dichiarato mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 È possibile fornire uno o più argomenti a un `ParamArray` parametro passando una matrice di dati appropriato, un elenco delimitato da virgole dei valori o non di tipo. Per ulteriori informazioni, vedere "Chiamata di ParamArray" [matrici di parametro](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Ogni volta che gestisce una matrice che può essere elevata per un periodo illimitato, c'è un rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri dal codice chiamante, è necessario verificarne la lunghezza e adottare se è troppo grande per l'applicazione.  
  
 Il modificatore `ParamArray` può essere usato nei contesti seguenti:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)  
 [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
