---
title: Tipi di metodi per la gestione delle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a02278abfb71efb2f31f239a89a22ad1c8ee7a18
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346278"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipi di metodi per la gestione delle stringhe in Visual Basic
Esistono diversi modi per analizzare e modificare le stringhe. Alcuni dei metodi sono parte del linguaggio Visual Basic e altri sono intrinseci nella classe `String`.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Lingua Visual Basic e .NET Framework  
 Visual Basic metodi vengono utilizzati come funzioni intrinseche del linguaggio. Possono essere usati senza qualificazione nel codice. Nell'esempio seguente viene illustrato l'uso tipico di un Visual Basic comando di manipolazione delle stringhe:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 In questo esempio, la funzione `Mid` esegue un'operazione diretta su `aString` e assegna il valore a `bString`.  
  
 Per un elenco dei metodi di modifica delle stringhe Visual Basic, vedere [Riepilogo della modifica delle stringhe](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Metodi condivisi e metodi di istanza  
 È anche possibile modificare le stringhe con i metodi della classe `String`. Esistono due tipi di metodi in `String`: metodi *condivisi* e metodi di *istanza* .  
  
#### <a name="shared-methods"></a>Metodi condivisi  
 Un metodo condiviso è un metodo che deriva dalla classe `String` stessa e non richiede l'uso di un'istanza di tale classe. Questi metodi possono essere qualificati con il nome della classe (`String`) anziché con un'istanza della classe `String`. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 Nell'esempio precedente, il metodo <xref:System.String.Copy%2A?displayProperty=nameWithType> è un metodo statico che agisce su un'espressione a cui viene assegnato e assegna al `bString`il valore risultante.  
  
#### <a name="instance-methods"></a>Metodi di istanza  
 I metodi di istanza, al contrario, derivano da una particolare istanza di `String` e devono essere qualificati con il nome dell'istanza. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo è un metodo dell'istanza di `String` (ovvero `aString`). Esegue un'operazione su `aString` e assegna tale valore a `bString`.  
  
 Per ulteriori informazioni, vedere la documentazione relativa alla classe <xref:System.String>.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
