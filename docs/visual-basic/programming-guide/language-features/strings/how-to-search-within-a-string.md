---
title: "Procedura: Cercare all'interno di una stringa (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: b690aa78a2cf07b0db5bdd28d7d71ed4a79fbf61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032084"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Procedura: Cercare all'interno di una stringa (Visual Basic)
Questo esempio chiama il <xref:System.String.IndexOf%2A> metodo su un <xref:System.String> per segnalare l'indice della prima occorrenza di una sottostringa.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un' `Imports` istruzione che specifica il <xref:System> dello spazio dei nomi. Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il <xref:System.String.IndexOf%2A> metodo segnala la posizione del primo carattere della prima occorrenza della sottostringa. L'indice è basato su 0, ovvero che il primo carattere della stringa ha indice 0.  
  
 Se <xref:System.String.IndexOf%2A> non trova la sottostringa, restituisce -1.  
  
 Il <xref:System.String.IndexOf%2A> metodo tra maiuscole e minuscole e Usa le impostazioni cultura correnti.  
  
 Per un controllo ottimale degli errori, è possibile racchiudere la stringa di ricerca nel `Try` blocco di un [Try... Catch... Istruzione finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) costruzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.IndexOf%2A>
- [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Stringhe](../../../../visual-basic/programming-guide/language-features/strings/index.md)
