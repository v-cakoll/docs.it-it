---
title: Nozioni fondamentali sulle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 935926b8b83afa47c20ea68aecd6bc8c40bd0234
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363697"
---
# <a name="string-basics-in-visual-basic"></a>Nozioni fondamentali sulle stringhe in Visual Basic
Il tipo di dati `String` rappresenta una serie di caratteri, ognuno dei quali, a sua volta, rappresenta un'istanza del tipo di dati `Char`. In questo argomento vengono introdotti i concetti di base delle stringhe in Visual Basic.  
  
## <a name="string-variables"></a>Variabili di tipo String  
 È possibile assegnare a un'istanza di una stringa un valore letterale che rappresenta una serie di caratteri. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 Una variabile `String` può accettare anche qualsiasi espressione che restituisca una stringa. Di seguito sono riportati alcuni esempi.  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 Qualsiasi valore letterale assegnato a una variabile `String` deve essere racchiuso tra virgolette (""). Questo implica che all'interno di una stringa le virgolette non possono essere rappresentate dal segno di virgolette. Il codice seguente, ad esempio, causa un errore di compilazione:  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 L'errore è determinato dal fatto che durante la compilazione la stringa viene considerata terminata dopo il secondo segno di virgolette e il resto della stringa è interpretato come codice. Per risolvere questo problema, Visual Basic interpreta due virgolette in un valore letterale stringa come una virgoletta singola nella stringa. L'esempio seguente illustra il modo corretto per inserire le virgolette in una stringa:   
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 Nell'esempio precedente, la coppia di virgolette che precede la parola `Look` diventa un segno di virgolette nella stringa. Le tre serie di virgolette alla fine della riga rappresentano le virgolette appartenenti alla stringa seguite dal carattere di terminazione della stringa.  
  
 I valori letterali stringa possono contenere più righe:  
  
```vb  
Dim x = "hello  
world"  
```  
  
 La stringa risultante contiene le sequenze di nuove righe usate nel valore letterale stringa (vbcr, vbcrlf e così via).  Non è più necessario usare la soluzione alternativa precedente:  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a>Caratteri nelle stringhe  
 Una stringa può essere considerata una serie di valori `Char`. Il tipo `String` è dotato di funzioni predefinite che consentono di eseguire numerose manipolazioni della stringa, simili a quelle consentite dalle matrici. Come tutte le matrici in .NET Framework, si tratta di matrici in base zero. Per fare riferimento a un carattere specifico di una stringa è possibile usare la proprietà `Chars`, che consente di accedere a un carattere in base alla sua posizione all'interno della stringa. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 Nell'esempio precedente, la proprietà `Chars` della stringa restituisce il quarto carattere della stringa, ovvero `D`, e lo assegna a `myChar`. È anche possibile ottenere la lunghezza di una particolare stringa mediante la proprietà `Length`. Se è necessario eseguire su una stringa più manipolazioni analoghe a quelle consentite nelle matrici, è possibile convertire la stringa in una matrice di istanze di `Char` usando la funzione `ToCharArray` della stringa. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 La variabile `myArray` ora contiene una matrice di istanze di `Char`, ognuna delle quali rappresenta un carattere di `myString`.  
  
## <a name="the-immutability-of-strings"></a>Immutabilità delle stringhe  
 Una stringa è *immutabile*, quindi il suo valore non può essere modificato dopo che è stato creato. Questo non impedisce tuttavia di assegnare più valori a una variabile di tipo String. Prendere in considerazione gli esempi seguenti:  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 In questo esempio, dopo aver creato una variabile stringa, le viene assegnato un valore che successivamente viene modificato.   
  
 Più precisamente, nella prima riga viene creata un'istanza di tipo `String` cui viene assegnato il valore `This string is immutable`. Nella seconda riga dell'esempio viene creata una nuova istanza a cui viene assegnato il valore `Or is it?`. Il riferimento alla prima istanza viene quindi ignorato e con la variabile stringa viene archiviato il riferimento alla nuova istanza.   
  
 A differenza di altri tipi di dati intrinseci, `String` è un tipo riferimento. Quando una variabile di tipo riferimento viene passata come argomento di una funzione o di una subroutine, invece del valore effettivo della stringa viene passato un riferimento all'indirizzo di memoria in cui sono archiviati i dati Nell'esempio precedente, quindi, il nome della variabile rimane lo stesso, ma punta a un'istanza nuova e diversa della classe `String`, che contiene il nuovo valore.   
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle stringhe in Visual Basic](introduction-to-strings.md)
- [Tipo di dati String](../../../language-reference/data-types/string-data-type.md)
- [Tipo di dati Char](../../../language-reference/data-types/char-data-type.md)
- [Operazioni di base sulle stringhe](../../../../standard/base-types/basic-string-operations.md)
