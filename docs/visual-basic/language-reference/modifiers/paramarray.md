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
ms.openlocfilehash: 8fc5d1afd9e9723e6b3c58e100b0519ef8fdfab4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968368"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato. `ParamArray`può essere usato solo nell'ultimo parametro di un elenco di parametri.  
  
## <a name="remarks"></a>Note  
 `ParamArray`consente di passare un numero arbitrario di argomenti alla procedura. Un `ParamArray` parametro viene sempre dichiarato utilizzando [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 È possibile specificare uno o più argomenti per un `ParamArray` parametro passando una matrice del tipo di dati appropriato, un elenco delimitato da virgole di valori o nulla. Per informazioni dettagliate, vedere la sezione relativa alla chiamata a ParamArray in [matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione. Se si accetta una matrice di parametri dal codice chiamante, è necessario testarne la lunghezza ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.  
  
 Il modificatore `ParamArray` può essere usato nei contesti seguenti:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
