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
ms.openlocfilehash: 54f7dcd7de28e8aaa5376bb4ddd67fd53518511e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481611"
---
# <a name="string-data-type-visual-basic"></a>Tipo di dati String (Visual Basic)
Contiene sequenze di punti di codice (a 2 byte) a 16 bit senza segno quell'intervallo compreso tra 0 e 65535. Ciascuna *punto di codice*, o il codice carattere rappresenta un singolo carattere Unicode. Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) i caratteri Unicode.  
  
## <a name="remarks"></a>Note  
 Usare la `String` tipo di dati per contenere più caratteri senza l'overhead di gestione di matrice dei `Char()`, una matrice di `Char` elementi.  
  
 Il valore predefinito `String` è `Nothing` (un riferimento null). Si noti che ciò non corrisponde alla stringa vuota (valore `""`).  
  
## <a name="unicode-characters"></a>Caratteri Unicode  
 I punti di 128 codice (0-127) prima di Unicode corrispondono alle lettere e simboli di una tastiera US standard. Questi primi punti di 128 codice sono identici a quelli definisce il set di caratteri ASCII. I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, ad esempio lettere dell'alfabeto basati sull'alfabeto latino, accenti, i simboli di valuta e le frazioni. Unicode utilizza i punti di codice rimanenti (256 e 65535) per un'ampia gamma di simboli. Questo include il carattere di testo in tutto il mondo, i segni diacritici e simboli matematici e tecnici.  
  
 È possibile usare i metodi, ad esempio <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un singolo carattere in un `String` variabile per determinarne la classificazione di Unicode.  
  
## <a name="format-requirements"></a>Requisiti di formato  
 È necessario racchiudere una `String` letterale racchiusa tra virgolette (`" "`). Se è necessario includere una virgoletta come uno dei caratteri nella stringa, è utilizzare due virgolette contigue (`""`). Questa condizione è illustrata nell'esempio seguente.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Si noti che le virgolette contigue che rappresentano un segno di virgolette nella stringa di sono indipendenti dalle virgolette che avviano e terminano le `String` letterale.  
  
## <a name="string-manipulations"></a>Manipolazioni di stringa  
 Una volta che si assegna una stringa in un `String` variabile, tale stringa viene *immutabile*, che significa che è possibile modificare la lunghezza o il contenuto. Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e Ignora quella precedente. Il `String` variabile fa quindi riferimento alla nuova stringa.  
  
 È possibile modificare il contenuto di un `String` variabile tramite un'ampia gamma di funzioni di stringa. Nell'esempio seguente viene illustrato il <xref:Microsoft.VisualBasic.Strings.Left%2A> (funzione)  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una stringa creata da un altro componente può essere completata con spazi iniziali o finali. Se si riceve una stringa di questo tipo, è possibile usare la <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> funzioni rimuovere gli spazi.  
  
 Per altre informazioni sulle stringhe, vedere [stringhe](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Numeri negativi.** Tenere presente che i caratteri inclusi in `String` non firmati e non può rappresentare i valori negativi. In ogni caso, è consigliabile non usare `String` per contenere valori numerici.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che caratteri della stringa hanno una larghezza di dati diversi (8 bit) in altri ambienti. Se si passa un argomento di stringa di caratteri a 8 bit a un componente, dichiararlo come `Byte()`, una matrice di `Byte` gli elementi, invece di `String` nel nuovo codice Visual Basic.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo identificatore `$` a qualsiasi identificatore, se ne determina la `String` tipo di dati. `String` non include alcun carattere di tipo di valore letterale. Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette (`" "`) come `String`.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la <xref:System.String?displayProperty=nameWithType> classe.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)  
 [Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
