---
title: Istruzione Mid (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963542"
---
# <a name="mid-statement"></a>Istruzione Mid
Sostituisce un numero specificato di caratteri in una `String` variabile con caratteri di un'altra stringa.  
  
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
 Richiesto. Nome della `String` variabile da modificare.  
  
 `Start`  
 Richiesto. `Integer`espressione. Posizione del carattere `Target` in in cui inizia la sostituzione del testo. `Start`Usa un indice in base uno.  
  
 `Length`  
 facoltativo. `Integer`espressione. Numero di caratteri da sostituire. Se omesso, `String` viene utilizzato tutto.  
  
 `StringExpression`  
 Richiesto. `String`espressione che sostituisce parte di `Target`.  
  
## <a name="exceptions"></a>Eccezioni  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`< = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Note  
 Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.  
  
 Visual Basic dispone di <xref:Microsoft.VisualBasic.Strings.Mid%2A> una funzione e `Mid` di un'istruzione. Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma `Mid` la funzione restituisce i caratteri mentre `Mid` l'istruzione sostituisce i caratteri. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> L' `MidB` istruzione di versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri. Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set). Tutte le stringhe di Visual Basic sono in formato `MidB` Unicode e non sono più supportate.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene `Mid` utilizzata l'istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:** `Strings`  
  
 **Assembly** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Introduzione alle stringhe in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
