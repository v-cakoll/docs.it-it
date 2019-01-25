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
ms.openlocfilehash: 47034b3699f4dfee67d36e72d4b22898d469c900
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700299"
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
 Obbligatorio. Nome del `String` variabile da modificare.  
  
 `Start`  
 Obbligatorio. `Integer` espressione. Posizione del carattere in `Target` dove inizia la sostituzione di testo. `Start` Usa un indice in base uno.  
  
 `Length`  
 Facoltativo. `Integer` espressione. Numero di caratteri da sostituire. Se omesso, tutti `String` viene usato.  
  
 `StringExpression`  
 Obbligatorio. `String` espressione che sostituisce parte di `Target`.  
  
## <a name="exceptions"></a>Eccezioni  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Note  
 Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target`.  
  
 Visual Basic ha un <xref:Microsoft.VisualBasic.Strings.Mid%2A> funzione e un `Mid` istruzione. Questi elementi funzionano entrambi in un numero specificato di caratteri in una stringa, ma il `Mid` funzione restituisce i caratteri, mentre il `Mid` istruzione sostituisce i caratteri. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  Il `MidB` istruzione delle versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché in caratteri. Viene utilizzato principalmente per la conversione di stringhe nelle applicazioni di double byte character set (DBCS). Tutte le stringhe di Visual Basic sono in formato Unicode, e `MidB` non è più supportata.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri da un'altra stringa.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modulo:** `Strings`  
  
 **Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Introduzione alle stringhe in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
