---
title: Conversione boxing di tipi nullable (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
ms.openlocfilehash: e2c7602bf45f1861d3a32a73824e9fedf0a4d29d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="boxing-nullable-types-c-programming-guide"></a>Conversione boxing di tipi nullable (Guida per programmatori C#)
Gli oggetti basati su tipi nullable sono boxed solo se l'oggetto è diverso da null. Se <xref:System.Nullable%601.HasValue%2A> è `false`, il riferimento all'oggetto viene assegnato a `null` anziché alla conversione boxing. Ad esempio:  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 Se l'oggetto è diverso da null (ovvero se <xref:System.Nullable%601.HasValue%2A> è `true`) viene eseguita la conversione boxing, ma solo il tipo sottostante su cui è basato l'oggetto è boxed. La conversione boxing di un tipo valore nullable diverso da null converte il tipo valore stesso e non <xref:System.Nullable%601?displayProperty=nameWithType>, usato per il wrapping del tipo valore. Ad esempio:  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 I due oggetti boxed sono identici a quelli creati dalla conversione boxing di tipi non nullable. E, proprio come i tipi boxed non nullable, possono essere boxed in tipi nullable, come illustrato nell'esempio seguente:  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>Note  
 Il comportamento di tipi nullable boxed offre due vantaggi:  
  
1.  È possibile testare gli oggetti nullable e la relativa controparte boxed per i valori null:  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  I tipi nullable boxed supportano la funzionalità del tipo sottostante:  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)  
 [Procedura: Identificare un tipo nullable](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
