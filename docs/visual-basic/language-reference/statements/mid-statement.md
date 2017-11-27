---
title: Istruzione Mid
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mid-statement"></a>Istruzione Mid
Sostituisce un numero specificato di caratteri in un `String` variabili con i caratteri da un'altra stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Parti  
 `Target`  
 Obbligatorio. Nome di `String` variabile da modificare.  
  
 `Start`  
 Obbligatorio. `Integer`espressione. Posizione del carattere in `Target` in cui inizia la sostituzione di testo. `Start`utilizza un indice in base uno.  
  
 `Length`  
 Parametro facoltativo. `Integer`espressione. Numero di caratteri da sostituire. Se omesso, tutti i `String` viene utilizzato.  
  
 `StringExpression`  
 Obbligatorio. `String`espressione che sostituisce una parte di `Target`.  
  
## <a name="exceptions"></a>Eccezioni  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Note  
 Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.  
  
 Visual Basic è disponibile un <xref:Microsoft.VisualBasic.Strings.Mid%2A> (funzione) e un `Mid` istruzione. Questi elementi entrambi funzionano su un numero specificato di caratteri in una stringa, ma la `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché come caratteri. Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS). Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:**`Strings`  
  
 **Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [Stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Introduzione alle stringhe in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
