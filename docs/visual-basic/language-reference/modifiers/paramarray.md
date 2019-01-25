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
ms.openlocfilehash: 16a69e547d14c619d427aa8860e9bf4002b6db04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703601"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato. `ParamArray` può essere utilizzato solo sull'ultimo parametro dell'elenco di parametri.  
  
## <a name="remarks"></a>Note  
 `ParamArray` Consente di passare un numero arbitrario di argomenti per la procedura. Oggetto `ParamArray` parametro viene sempre dichiarato usando [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 È possibile fornire uno o più argomenti per un `ParamArray` passando una matrice dei dati appropriati tipo di parametro, un elenco delimitato da virgole di valori o niente affatto. Per informazioni dettagliate, vedere la sezione "Chiamata ParamArray" nella [matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione. Se si accetta una matrice di parametri dal codice chiamante, occorre verificarne la lunghezza ed eseguire i passaggi appropriati, se è troppo grande per l'applicazione.  
  
 Il modificatore `ParamArray` può essere usato nei contesti seguenti:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
