---
title: Come determinare se una stringa rappresenta una guida per la C# programmazione di valori numerici
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: bd89024a0a9bd62927d2d5e0eda248b57bb7d21d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711922"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a>Come determinare se una stringa rappresenta un valore numerico (C# guida per programmatori)
Per determinare se una stringa è una rappresentazione valida di un tipo numerico specificato, usare il metodo statico `TryParse` che viene implementato da tutti i tipi numerici primitivi e anche da tipi quali <xref:System.DateTime> e <xref:System.Net.IPAddress>. L'esempio seguente illustra come determinare se "108" è un tipo [int](../../language-reference/builtin-types/integral-numeric-types.md) valido.  
  
```csharp  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Se la stringa contiene caratteri non numerici o se il valore numerico è o troppo grande o troppo piccolo per un determinato tipo specificato, `TryParse` restituisce false e imposta il parametro out su zero. In caso contrario, restituisce true e imposta il parametro out sul valore numerico della stringa.  
  
> [!NOTE]
> È possibile che una stringa contenga solo caratteri numeri e che non sia tuttavia valida per il tipo per il quale si usa il metodo `TryParse`. Ad esempio, "256" non è un valore valido per `byte`, ma lo è per `int`. "98,6" non è un valore valido per `int` ma è un valore `decimal` valido.  
  
## <a name="example"></a>Esempio  
 Gli esempi seguenti illustrano come usare `TryParse` con rappresentazioni di stringa di valori `long`, `byte` e `decimal`.  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 I tipi numerici primitivi implementano anche il metodo statico `Parse`, che genera un'eccezione se la stringa non è un numero valido. Il metodo `TryParse` è in genere più efficiente in quanto restituisce false se il numero non è valido.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Usare sempre i metodi `TryParse` o `Parse` per convalidare l'input dell'utente da controlli, come caselle di testo e caselle combinate.  
  
## <a name="see-also"></a>Vedere anche

- [Come convertire una matrice di byte in un valore int](../types/how-to-convert-a-byte-array-to-an-int.md)
- [Come convertire una stringa in un numero](../types/how-to-convert-a-string-to-a-number.md)
- [Come eseguire la conversione tra stringhe esadecimali e tipi numerici](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [Analisi di stringhe numeriche](../../../standard/base-types/parsing-numeric.md)
- [Formattazione di tipi](../../../standard/base-types/formatting-types.md)
