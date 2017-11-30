---
title: 'Procedura: cercare all''interno di una stringa (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c828d0b32fdf90e121e9d5da0bb60ab11c212f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Procedura: cercare all'interno di una stringa (Visual Basic)
Questo esempio viene chiamato il <xref:System.String.IndexOf%2A> metodo su un <xref:System.String> per segnalare l'indice della prima occorrenza di una sottostringa.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un `Imports` istruzione specificando il <xref:System> dello spazio dei nomi. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.String.IndexOf%2A> metodo indica la posizione del primo carattere della prima occorrenza della sottostringa. L'indice è basato su 0, ovvero che il primo carattere della stringa ha indice 0.  
  
 Se <xref:System.String.IndexOf%2A> non trova la sottostringa, restituisce -1.  
  
 Il <xref:System.String.IndexOf%2A> metodo tra maiuscole e minuscole e utilizza le impostazioni cultura correnti.  
  
 Per un controllo ottimale degli errori, è consigliabile racchiudere la stringa di ricerca nel `Try` blocco di un [provare... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) costruzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String.IndexOf%2A>  
 [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
