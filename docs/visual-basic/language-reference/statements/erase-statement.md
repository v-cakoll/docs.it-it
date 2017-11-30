---
title: Istruzione Erase (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a>Istruzione Erase (Visual Basic)
Utilizzato per rilasciare le variabili di matrice e deallocare la memoria utilizzata per i relativi elementi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>Parti  
 `arraylist`  
 Obbligatorio. Elenco di variabili di matrice da cancellare. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
## <a name="remarks"></a>Note  
 Il `Erase` istruzione può essere utilizzata solo a livello di routine. Ciò significa che è possibile rilasciare le matrici all'interno di una stored procedure, ma non a livello di classe o modulo.  
  
 Il `Erase` istruzione equivale all'assegnazione `Nothing` per ogni variabile di matrice.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Erase` istruzione per cancellare due matrici e liberare la memoria (1000 e 100 elementi, rispettivamente). Il `ReDim` istruzione assegna quindi una nuova istanza di matrice alla matrice tridimensionale.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Nothing](../../../visual-basic/language-reference/nothing.md)  
 [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
