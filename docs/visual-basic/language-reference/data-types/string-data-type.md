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
ms.openlocfilehash: 894638bbe50dad2cae1f74a2f7b7fe006f029d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="string-data-type-visual-basic"></a>Tipo di dati String (Visual Basic)
Contiene le sequenze di punti di codice di (2 byte) senza segno a 16 bit tale intervallo compreso tra 0 e 65535. Ogni *punto di codice*, o codice di carattere, rappresenta un singolo carattere Unicode. Una stringa può contenere da 0 a due miliardi (2 ^ 31) caratteri Unicode.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `String` il tipo di dati per contenere più caratteri senza l'overhead di gestione di matrice di `Char()`, una matrice di `Char` elementi.  
  
 Il valore predefinito di `String` è `Nothing` (un riferimento null). Si noti che questo non è lo stesso come una stringa vuota (valore `""`).  
  
## <a name="unicode-characters"></a>Caratteri Unicode  
 I primo 128 punti di codice (0-127) di Unicode corrispondono alle lettere e simboli di tastiera standard. Questi primi punti di 128 codice sono gli stessi di quelli definisce il set di caratteri ASCII. I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, quali lettere dell'alfabeto latino, accenti, simboli di valuta e le frazioni di secondo. Unicode utilizza i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli. Sono inclusi caratteri testuali in tutto il mondo, segni diacritici e simboli matematici e tecnici.  
  
 È possibile utilizzare i metodi, ad esempio <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un singolo carattere in un `String` variabile per determinarne la classificazione di Unicode.  
  
## <a name="format-requirements"></a>Requisiti di formato  
 È necessario racchiudere un `String` letterale racchiusa tra virgolette (`" "`). Se è necessario includere un segno di virgolette come uno dei caratteri nella stringa, utilizzare due virgolette contigue (`""`). Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Si noti che le virgolette contigue che rappresentano un segno di virgolette nella stringa sono indipendenti tra le virgolette che avviano e terminano le `String` letterale.  
  
## <a name="string-manipulations"></a>Modifiche di stringa  
 Dopo aver assegnato una stringa a un `String` variabile, tale stringa è *non modificabile*, pertanto non è possibile modificare la lunghezza o il contenuto. Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e la precedente viene abbandonata. Il `String` variabile fa quindi riferimento alla nuova stringa.  
  
 È possibile modificare il contenuto di un `String` variabile tramite un'ampia gamma di funzioni di stringa. Nell'esempio seguente viene illustrato il <xref:Microsoft.VisualBasic.Strings.Left%2A> (funzione)  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una stringa creata da un altro componente potrebbe essere riempita con spazi iniziali o finali. Se si riceve tale stringa, è possibile utilizzare il <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> funzioni rimuovere gli spazi.  
  
 Per ulteriori informazioni sulle stringhe, vedere [stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Numeri negativi.** Tenere presente che i caratteri inclusi in `String` non sono firmati e non può rappresentare valori negativi. In ogni caso, è consigliabile non utilizzare `String` per contenere valori numerici.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i caratteri di stringa hanno un'ampiezza dei dati diversa (8 bit) in altri ambienti. Se si passa un argomento stringa di caratteri a 8 bit a tale componente, dichiararla come `Byte()`, una matrice di `Byte` elementi, invece di `String` nel nuovo codice Visual Basic.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo identificatore `$` a qualsiasi identificatore indica al sistema di `String` tipo di dati. `String` è presente alcun carattere di tipo di valore letterale. Il compilatore considera tuttavia i valori letterali racchiusi tra virgolette (`" "`) come `String`.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la <xref:System.String?displayProperty=nameWithType> classe.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
