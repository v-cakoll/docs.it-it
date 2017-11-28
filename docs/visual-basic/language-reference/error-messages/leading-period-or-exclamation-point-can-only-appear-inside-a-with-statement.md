---
title: "Interlinea &#39;. &#39; o &#39;! &#39; può trovarsi solo all'interno di un &#39; Con &#39; istruzione"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Interlinea &#39;. &#39; o &#39;! &#39; può trovarsi solo all'interno di un &#39; Con &#39; istruzione
Un punto (.) o un punto esclamativo (!) che non è all'interno un `With` blocco si verifica senza un'espressione a sinistra. Accesso ai membri (`.`) e accesso ai membri dizionario (`!`) richiedono un'espressione che specifica l'elemento che contiene il membro. Questo deve apparire immediatamente a sinistra della funzione di accesso o come destinazione di un `With` blocco che contiene l'accesso al membro.  
  
 **ID errore:** BC30157  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che il `With` blocco sia formattato correttamente.  
  
2.  Se è presente alcun `With` di blocco, aggiungere un'espressione a sinistra della funzione di accesso che restituisce un elemento definito contenente il membro.  
  
## <a name="see-also"></a>Vedere anche  
 [Caratteri speciali nel codice](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
