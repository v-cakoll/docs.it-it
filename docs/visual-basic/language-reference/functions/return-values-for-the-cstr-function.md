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
ms.openlocfilehash: 5312734633eea12aacd7e61afba616d31e06cd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598524"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valori restituiti dalla funzione CStr (Visual Basic)
Nella tabella seguente vengono descritti i valori restituiti per `CStr` per diversi tipi di dati di `expression`.  
  
|Se `expression` è di tipo|Valori restituiti `CStr`|  
|-----------------------------|--------------------|  
|[Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Una stringa contenente "True" o "False".|  
|[Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Stringa contenente un `Date` valore (data e ora) nel formato di data breve del sistema.|  
|[Tipi di dati numerici](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Stringa che rappresenta il numero.|  
  
## <a name="cstr-and-date"></a>Data e CStr  
 Il `Date` tipo contiene sempre le informazioni sia data e ora. Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora. `CStr` non include valori neutri nella stringa risultante. Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30:00 AM"; le informazioni sulla data viene eliminate. Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  Il `CStr` funzione esegue la conversione in base alle impostazioni cultura correnti per l'applicazione. Per ottenere la rappresentazione di stringa di un numero in una lingua specifica, utilizzare il numero `ToString(IFormatProvider)` metodo. Ad esempio, utilizzare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` per un `String`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)
