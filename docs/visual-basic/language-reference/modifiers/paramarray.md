---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: e3c24818ea87884a0dd9b42c604e13e16ca6d3d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391820"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato. `ParamArray`può essere usato solo nell'ultimo parametro di un elenco di parametri.  
  
## <a name="remarks"></a>Commenti  
 `ParamArray`consente di passare un numero arbitrario di argomenti alla procedura. Un `ParamArray` parametro viene sempre dichiarato utilizzando [ByVal](byval.md).  
  
 È possibile specificare uno o più argomenti per un `ParamArray` parametro passando una matrice del tipo di dati appropriato, un elenco delimitato da virgole di valori o nulla. Per informazioni dettagliate, vedere la sezione relativa alla chiamata a ParamArray in [matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione. Se si accetta una matrice di parametri dal codice chiamante, è necessario testarne la lunghezza ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.  
  
 Il modificatore `ParamArray` può essere usato nei contesti seguenti:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Istruzione Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Istruzione Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../keywords/index.md)
- [Matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md)
