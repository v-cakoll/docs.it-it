---
title: Istruzione Stop (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b7f04214234837a86bf0c77c0d7b6934e2babd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="stop-statement-visual-basic"></a>Istruzione Stop (Visual Basic)
Sospende l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire `Stop` istruzioni in un punto qualsiasi nelle procedure per sospendere l'esecuzione. Utilizzo di `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.  
  
 Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o deselezionare tutte le variabili, a meno che non viene rilevata in un file eseguibile compilato (.exe).  
  
> [!NOTE]
>  Se il `Stop` viene rilevata l'istruzione nel codice che è in esecuzione all'esterno dell'ambiente di sviluppo integrato (IDE), il debugger viene richiamato. Questo vale indipendentemente dal fatto che il codice è stato compilato in modalità di debug o finale.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Stop` istruzione per sospendere l'esecuzione per ogni iterazione di `For...Next` ciclo.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
