---
title: 'How to: Convert Between Hexadecimal Strings and Numeric Types - C# Programming Guide'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 8b72734f9b617fed2ff65977c9a0e60f46424ae8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429448"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Procedura: eseguire la conversione tra stringhe esadecimali e tipi numerici (Guida per programmatori C#)
In questi esempi viene mostrato come effettuare le seguenti attività:  
  
- Ottenere il valore esadecimale di ogni carattere in un oggetto [string](../../language-reference/builtin-types/reference-types.md).  
  
- Ottenere l'oggetto [char](../../language-reference/builtin-types/char.md) che corrisponde a ogni valore in una stringa esadecimale.  
  
- Convertire un oggetto `string` esadecimale in un oggetto [int](../../language-reference/builtin-types/integral-numeric-types.md).  
  
- Convertire un oggetto `string` esadecimale in un oggetto [float](../../language-reference/builtin-types/floating-point-numeric-types.md).  
  
- Convertire una matrice di [byte](../../language-reference/builtin-types/integral-numeric-types.md) in un oggetto `string` esadecimale.  
  
## <a name="example"></a>Esempio  
 Questo esempio restituisce il valore esadecimale di ogni carattere in un oggetto `string`. Prima viene analizzato l'oggetto `string` in una matrice di caratteri. Poi viene chiamato <xref:System.Convert.ToInt32%28System.Char%29> in ogni carattere per ottenere il rispettivo valore numerico. Il numero viene infine formattato come esadecimale in un oggetto `string`.  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a>Esempio  
 Questo esempio analizza un oggetto `string` di valori esadecimali e restituisce il carattere corrispondente a ogni valore esadecimale. Prima viene chiamato il metodo [Split(Char\[\])](xref:System.String.Split(System.Char[])) per ottenere ogni valore esadecimale come singolo oggetto `string` in una matrice. Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code. La prima tecnica usa `string` che restituisce il carattere corrispondente all'argomento Integer come <xref:System.Char.ConvertFromUtf32%28System.Int32%29>. La seconda tecnica esegue il cast in modo esplicito del valore `int` a un valore [char](../../language-reference/builtin-types/char.md).  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra un altro modo per convertire un valore esadecimale `string` in un Integer, chiamando il metodo <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come convertire un tipo `string` esadecimale in [float](../../language-reference/builtin-types/floating-point-numeric-types.md) usando la classe <xref:System.BitConverter?displayProperty=nameWithType> e il metodo <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come convertire una matrice [byte](../../language-reference/builtin-types/integral-numeric-types.md) in una stringa esadecimale tramite la classe <xref:System.BitConverter?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a>Vedere anche

- [Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md)
- [Tipi](./index.md)
- [Procedura: Determinare se una stringa rappresenta un valore numerico](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
