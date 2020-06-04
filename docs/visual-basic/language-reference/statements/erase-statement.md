---
title: Istruzione Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 31aeaf822bc9c1de59a5c5f68406c6521216ae0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404719"
---
# <a name="erase-statement-visual-basic"></a>Istruzione Erase (Visual Basic)
Usato per rilasciare le variabili di matrice e deallocare la memoria usata per i relativi elementi.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a>Parti  
 `arraylist`  
 Obbligatorio. Elenco di variabili di matrice da cancellare. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
## <a name="remarks"></a>Commenti  
 L' `Erase` istruzione può essere visualizzata solo a livello di routine. Ciò significa che è possibile rilasciare matrici all'interno di una routine ma non a livello di classe o di modulo.  
  
 L' `Erase` istruzione equivale all'assegnazione `Nothing` a ogni variabile di matrice.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Erase` istruzione per cancellare due matrici e liberare la relativa memoria (rispettivamente gli elementi di archiviazione 1000 e 100). L' `ReDim` istruzione assegna quindi una nuova istanza di matrice alla matrice tridimensionale.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Nothing](../nothing.md)
- [Istruzione ReDim](redim-statement.md)
