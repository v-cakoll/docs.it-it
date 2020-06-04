---
title: Tipo di dati String
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
ms.openlocfilehash: cd4b64c101ae56928e84a04649e49c17b6f4023c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415505"
---
# <a name="string-data-type-visual-basic"></a>Tipo di dati String (Visual Basic)

Include sequenze di punti di codice senza segno a 16 bit (2 byte) che variano da 0 a 65535. Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode. Una stringa può contenere da 0 a circa 2 miliardi (2 ^ 31) caratteri Unicode.  
  
## <a name="remarks"></a>Commenti  

 Usare il `String` tipo di dati per mantenere più caratteri senza l'overhead di gestione della matrice di `Char()` , una matrice di `Char` elementi.  
  
 Il valore predefinito di `String` è `Nothing` (un riferimento null). Si noti che questa operazione non corrisponde alla stringa vuota (valore `""` ).  
  
## <a name="unicode-characters"></a>Caratteri Unicode  

 I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti. Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII. I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni. Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli. Sono inclusi i caratteri testuali, i segni diacritici e i simboli matematici e tecnici in tutto il mondo.  
  
 È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un singolo carattere in una `String` variabile per determinare la relativa classificazione Unicode.  
  
## <a name="format-requirements"></a>Requisiti di formato  

 È necessario racchiudere un `String` valore letterale racchiuso tra virgolette ( `" "` ). Se è necessario includere una virgoletta come uno dei caratteri nella stringa, è possibile utilizzare due virgolette contigue ( `""` ). Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Si noti che le virgolette contigue che rappresentano le virgolette nella stringa sono indipendenti dalle virgolette che iniziano e terminano il `String` valore letterale.  
  
## <a name="string-manipulations"></a>Modifiche delle stringhe  

 Una volta assegnata una stringa a una `String` variabile, tale stringa non è *modificabile*, quindi non è possibile modificarne la lunghezza o il contenuto. Quando si modifica una stringa in qualsiasi modo, Visual Basic crea una nuova stringa e abbandona quella precedente. La `String` variabile fa quindi riferimento alla nuova stringa.  
  
 È possibile modificare il contenuto di una `String` variabile usando un'ampia gamma di funzioni di stringa. Nell'esempio seguente viene illustrata la <xref:Microsoft.VisualBasic.Strings.Left%2A> funzione  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una stringa creata da un altro componente potrebbe essere riempita con spazi iniziali o finali. Se si riceve una stringa di questo tipo, è possibile usare le <xref:Microsoft.VisualBasic.Strings.Trim%2A> <xref:Microsoft.VisualBasic.Strings.LTrim%2A> funzioni, e <xref:Microsoft.VisualBasic.Strings.RTrim%2A> per rimuovere questi spazi.  
  
 Per ulteriori informazioni sulle modifiche delle stringhe, vedere [stringhe](../../programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
- **Numeri negativi.** Tenere presente che i caratteri conservati da `String` non sono firmati e non possono rappresentare valori negativi. In ogni caso, è consigliabile non usare `String` per mantenere i valori numerici.  
  
- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i caratteri stringa hanno una larghezza dati diversa (8 bit) in altri ambienti. Se si passa un argomento stringa di caratteri a 8 bit a tale componente, dichiararlo come `Byte()` una matrice di `Byte` elementi, anziché `String` nel nuovo codice Visual Basic.  
  
- **Digitare i caratteri.** L'aggiunta del carattere di tipo identificatore `$` a qualsiasi identificatore forza il `String` tipo di dati. `String`non ha un carattere di tipo letterale. Tuttavia, il compilatore considera i valori letterali racchiusi tra virgolette ( `" "` ) come `String` .  
  
- **Tipo di framework.** Il tipo corrispondente nella .NET Framework è la <xref:System.String?displayProperty=nameWithType> classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [Tipo di dati Char](char-data-type.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
