---
title: Conversione boxing di tipi nullable (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 29fccba56f6758fdfd407fa1879baa9260b69187
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
