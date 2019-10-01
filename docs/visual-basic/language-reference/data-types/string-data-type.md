---
title: Tipo di dati String (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 6d2fd226735622de5cd7197060c05b8ac12b69f1
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696834"
---
# <a name="string-data-type-visual-basic"></a>Tipo di dati String (Visual Basic)
Include sequenze di punti di codice senza segno a 16 bit (2 byte) che variano da 0 a 65535. Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode. Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) caratteri Unicode.  
  
## <a name="remarks"></a>Note  
 Usare il tipo di dati `String` per mantenere più caratteri senza l'overhead di gestione della matrice di `Char()`, una matrice di elementi `Char`.  
  
 Il valore predefinito di `String` è `Nothing` (un riferimento null). Si noti che non corrisponde alla stringa vuota (valore `""`).  
  
## <a name="unicode-characters"></a>Caratteri Unicode  
 I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti. Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII. I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni. Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli. Sono inclusi i caratteri testuali, i segni diacritici e i simboli matematici e tecnici in tutto il mondo.  
  
 È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> per un singolo carattere in una variabile `String` per determinare la relativa classificazione Unicode.  
  
## <a name="format-requirements"></a>Requisiti di formato  
 È necessario racchiudere un valore letterale `String` racchiuso tra virgolette (`" "`). Se è necessario includere una virgoletta come uno dei caratteri nella stringa, è possibile utilizzare due virgolette contigue (`""`). Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Si noti che le virgolette contigue che rappresentano le virgolette nella stringa sono indipendenti dalle virgolette che iniziano e terminano il valore letterale `String`.  
  
## <a name="string-manipulations"></a>Modifiche delle stringhe  
 Una volta assegnata una stringa a una variabile `String`, tale stringa non è *modificabile*e pertanto non è possibile modificarne la lunghezza o il contenuto. Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e abbandona quella precedente. La variabile `String` fa quindi riferimento alla nuova stringa.  
  
 È possibile modificare il contenuto di una variabile `String` usando un'ampia gamma di funzioni di stringa. Nell'esempio seguente viene illustrata la funzione <xref:Microsoft.VisualBasic.Strings.Left%2A>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una stringa creata da un altro componente potrebbe essere riempita con spazi iniziali o finali. Se si riceve una stringa di questo tipo, è possibile usare le funzioni <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> per rimuovere questi spazi.  
  
 Per ulteriori informazioni sulle modifiche delle stringhe, vedere [stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Numeri negativi.** Tenere presente che i caratteri contenuti in `String` non sono firmati e non possono rappresentare valori negativi. In ogni caso, è consigliabile non utilizzare `String` per mantenere i valori numerici.  
  
- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i caratteri stringa hanno una larghezza dati diversa (8 bit) in altri ambienti. Se si passa un argomento di stringa di caratteri a 8 bit a tale componente, dichiararlo come `Byte()`, una matrice di elementi `Byte`, invece di `String` nel nuovo codice Visual Basic.  
  
- **Digitare i caratteri.** L'aggiunta del carattere di tipo identificatore `$` a qualsiasi identificatore forza il tipo di dati `String`. `String` non contiene alcun carattere di tipo letterale. Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette (`" "`) come `String`.  
  
- **Tipo di Framework.** Il tipo corrispondente nella .NET Framework è la classe <xref:System.String?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
