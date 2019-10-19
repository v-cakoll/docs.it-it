---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 7dec2a859f664ee8dcbb305082ec33aeacbaccb4
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583393"
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
  
## <a name="remarks"></a>Note  
 L'istruzione `Erase` può essere visualizzata solo a livello di routine. Ciò significa che è possibile rilasciare matrici all'interno di una routine ma non a livello di classe o di modulo.  
  
 L'istruzione `Erase` equivale a assegnare `Nothing` a ogni variabile di matrice.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Erase` per cancellare due matrici e liberare la relativa memoria (rispettivamente gli elementi di archiviazione 1000 e 100). L'istruzione `ReDim` assegna quindi una nuova istanza di matrice alla matrice tridimensionale.  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
