---
title: Valori restituiti dalla funzione CStr (Visual Basic)
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
ms.openlocfilehash: cd525ea5a295411e509f3bc37285675d15a8c4f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930041"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valori restituiti dalla funzione CStr (Visual Basic)
Nella tabella seguente vengono descritti i valori restituiti `CStr` per per diversi tipi di `expression`dati di.  
  
|Se `expression` il tipo è|Valori restituiti `CStr`|  
|-----------------------------|--------------------|  
|[Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Stringa contenente "true" o "false".|  
|[Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Stringa contenente un `Date` valore (data e ora) nel formato di data breve del sistema.|  
|[Tipi di dati numerici](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Stringa che rappresenta il numero.|  
  
## <a name="cstr-and-date"></a>CStr e data  
 Il `Date` tipo contiene sempre le informazioni di data e ora. Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 gennaio dell'anno 1) come *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora. `CStr`non include valori neutri nella stringa risultante. Se ad esempio si esegue la `#January 1, 0001 9:30:00#` conversione in una stringa, il risultato sarà "9:30:00 AM"; le informazioni sulla data vengono annullate. Tuttavia, le informazioni sulla data sono ancora presenti nel valore `Date` originale e possono essere ripristinate con funzioni <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>come.  
  
> [!NOTE]
> La `CStr` funzione esegue la conversione in base alle impostazioni cultura correnti dell'applicazione. Per ottenere la rappresentazione di stringa di un numero in determinate impostazioni cultura, usare il `ToString(IFormatProvider)` metodo del numero. Ad esempio, usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> quando si converte un valore di `Double` tipo in `String`un oggetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)
