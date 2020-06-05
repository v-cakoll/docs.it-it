---
title: Istruzione Mid
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
ms.openlocfilehash: 90408fd8a8cfc9b74c8422d0571d61f8534403f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404452"
---
# <a name="mid-statement"></a>Istruzione Mid
Sostituisce un numero specificato di caratteri in una `String` variabile con caratteri di un'altra stringa.  
  
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
 Obbligatorio. Nome della `String` variabile da modificare.  
  
 `Start`  
 Obbligatorio. Espressione `Integer`. Posizione del carattere in in `Target` cui inizia la sostituzione del testo. `Start`Usa un indice in base uno.  
  
 `Length`  
 Facoltativa. Espressione `Integer`. Numero di caratteri da sostituire. Se omesso, `String` viene utilizzato tutto.  
  
 `StringExpression`  
 Obbligatorio. `String`espressione che sostituisce parte di `Target` .  
  
## <a name="exceptions"></a>Eccezioni  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start`<= 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Commenti  
 Il numero di caratteri sostituiti è sempre minore o uguale al numero di caratteri in `Target` .  
  
 Visual Basic dispone di una <xref:Microsoft.VisualBasic.Strings.Mid%2A> funzione e di un' `Mid` istruzione. Questi elementi operano entrambi su un numero specificato di caratteri in una stringa, ma la `Mid` funzione restituisce i caratteri mentre l' `Mid` istruzione sostituisce i caratteri. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> L' `MidB` istruzione di versioni precedenti di Visual Basic sostituisce una sottostringa in byte, anziché caratteri. Viene utilizzato principalmente per la conversione di stringhe in applicazioni DBCS (Double-byte character set). Tutte le stringhe di Visual Basic sono in formato Unicode e `MidB` non sono più supportate.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l' `Mid` istruzione per sostituire un numero specificato di caratteri in una variabile di stringa con caratteri di un'altra stringa.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Modulo:**`Strings`  
  
 **Assembly:** Libreria di runtime Visual Basic (in Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Stringhe](../../programming-guide/language-features/strings/index.md)
- [Introduzione alle stringhe in Visual Basic](../../programming-guide/language-features/strings/introduction-to-strings.md)
