---
title: "Istruzione non è valida all'interno di un'espressione lambda su più righe di metodo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords: BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80673fc7a1497b4148a6505d29581c6403115558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Istruzione non valida all'interno di un metodo/espressione lambda su più righe
L'istruzione non è valido all'interno di un `Sub`, `Function`, proprietà `Get`, o proprietà `Set` stored procedure. Alcune istruzioni possono essere inseriti a livello di modulo o classe. Altri, ad esempio `Option Strict`, è necessario essere a livello di spazio dei nomi e precedere tutte le altre dichiarazioni.  
  
 **ID errore:** BC30024  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere l'istruzione dalla routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Istruzione Set](../../../visual-basic/language-reference/statements/set-statement.md)
