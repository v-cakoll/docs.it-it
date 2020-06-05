---
title: Tipi di metodi per la gestione delle stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363759"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Tipi di metodi per la gestione delle stringhe in Visual Basic
Esistono diversi modi per analizzare e modificare le stringhe. Alcuni dei metodi fanno parte del linguaggio Visual Basic e altri sono intrinseci nella `String` classe.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Lingua Visual Basic e .NET Framework  
 Visual Basic metodi vengono utilizzati come funzioni intrinseche del linguaggio. Possono essere usati senza qualificazione nel codice. Nell'esempio seguente viene illustrato l'uso tipico di un Visual Basic comando di manipolazione delle stringhe:  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 In questo esempio, la `Mid` funzione esegue un'operazione diretta su `aString` e assegna il valore a `bString` .  
  
 Per un elenco dei metodi di modifica delle stringhe Visual Basic, vedere [Riepilogo della modifica delle stringhe](../../../language-reference/keywords/string-manipulation-summary.md).  
  
### <a name="shared-methods-and-instance-methods"></a>Metodi condivisi e metodi di istanza  
 È anche possibile modificare le stringhe con i metodi della `String` classe. In sono disponibili due tipi di metodi `String` : metodi *condivisi* e metodi di *istanza* .  
  
#### <a name="shared-methods"></a>Metodi condivisi  
 Un metodo condiviso è un metodo che deriva dalla `String` classe stessa e non richiede l'uso di un'istanza di tale classe. Questi metodi possono essere qualificati con il nome della classe ( `String` ) anziché con un'istanza della `String` classe. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 Nell'esempio precedente, il <xref:System.String.Copy%2A?displayProperty=nameWithType> metodo è un metodo statico che agisce su un'espressione a cui viene assegnato e che assegna il valore risultante a `bString` .  
  
#### <a name="instance-methods"></a>Metodi di istanza  
 I metodi di istanza, al contrario, derivano da una particolare istanza di `String` e devono essere qualificati con il nome dell'istanza. Ad esempio:  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 In questo esempio, il <xref:System.String.Substring%2A?displayProperty=nameWithType> metodo è un metodo dell'istanza di `String` (ovvero `aString` ). Esegue un'operazione su `aString` e assegna tale valore a `bString` .  
  
 Per ulteriori informazioni, vedere la documentazione relativa alla <xref:System.String> classe.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle stringhe in Visual Basic](introduction-to-strings.md)
