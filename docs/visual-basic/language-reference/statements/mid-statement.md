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
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581482"
---
# <a name="mid-statement"></a>Istruzione Mid
Sostituisce un numero specificato di caratteri in una variabile `String` con caratteri di un'altra stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Parti  
 `Target`  
 Obbligatorio. Nome della variabile `String` da modificare.  
  
 `Start`  
 Obbligatorio. espressione `Integer`. Posizione del carattere in `Target` in cui inizia la sostituzione del testo. `Start` utilizza un indice in base uno.  
  
 `Length`  
 Parametro facoltativo. espressione `Integer`. Numero di caratteri da sostituire. Se omesso, viene utilizzato tutto `String`.  
  
 `StringExpression`  
 Obbligatorio. espressione `String` che sostituisce parte del `Target`.  
  
## <a name="exceptions"></a>Eccezioni  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Note  
 Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.  
  
 Visual Basic dispone di una funzione <xref:Microsoft.VisualBasic.Strings.Mid%2A> e di un'istruzione `Mid`. Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma la funzione `Mid` restituisce i caratteri mentre l'istruzione `Mid` sostituisce i caratteri. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> L'istruzione `MidB` delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri. Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set). Tutte le stringhe di Visual Basic sono in formato Unicode e `MidB` non è più supportata.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l'istruzione `Mid` per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:** `Strings`  
  
 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Introduzione alle stringhe in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
