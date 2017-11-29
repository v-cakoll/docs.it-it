---
title: 'Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)
Quando è importante che un'applicazione mantenere l'utilizzo della memoria basso, esistono diverse circostanze. Eventi personalizzati consentono all'applicazione di utilizzare la memoria solo per gli eventi che gestisce.  
  
 Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo archiviare le informazioni sull'evento. Se una classe dispone di molti eventi inutilizzati, hanno inutilmente la memoria.  
  
 Anziché utilizzare l'implementazione predefinita di eventi disponibili in Visual Basic, è possibile utilizzare gli eventi personalizzati per gestire più attentamente l'utilizzo della memoria.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la classe utilizza un'istanza di <xref:System.ComponentModel.EventHandlerList> (classe), archiviati nel `Events` campo, per archiviare le informazioni sugli eventi in uso. Il <xref:System.ComponentModel.EventHandlerList> è una classe di elenco ottimizzata progettata per contenere delegati.  
  
 Tutti gli eventi della classe utilizzano il `Events` campo per tenere traccia di quali metodi sono la gestione di ogni evento.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ComponentModel.EventHandlerList>  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Procedura: Dichiarare eventi personalizzati per evitare il blocco](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
