---
title: Valori restituiti dalla funzione CStr
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349994"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valori restituiti dalla funzione CStr (Visual Basic)
Nella tabella seguente vengono descritti i valori restituiti per `CStr` per diversi tipi di dati di `expression`.  
  
|Se `expression` tipo è|Valori restituiti `CStr`|  
|-----------------------------|--------------------|  
|[Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Stringa contenente "true" o "false".|  
|[Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Stringa contenente un valore `Date` (data e ora) nel formato di data breve del sistema.|  
|[Tipi di dati numerici](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Stringa che rappresenta il numero.|  
  
## <a name="cstr-and-date"></a>CStr e data  
 Il tipo di `Date` contiene sempre le informazioni di data e ora. Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 gennaio dell'anno 1) come *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora. `CStr` non include valori neutri nella stringa risultante. Se ad esempio si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato sarà "9:30:00 AM"; le informazioni sulla data vengono omesse. Tuttavia, le informazioni sulla data sono ancora presenti nel valore di `Date` originale e possono essere ripristinate con funzioni come <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
> La funzione `CStr` esegue la conversione in base alle impostazioni cultura correnti dell'applicazione. Per ottenere la rappresentazione di stringa di un numero in determinate impostazioni cultura, usare il metodo `ToString(IFormatProvider)` del numero. Ad esempio, usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` in un `String`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)
