---
title: '#define - Riferimenti per C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: 7457b05ae827675969398792bcb02f025f3028fb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712585"
---
# <a name="define-c-reference"></a>#define (Riferimenti per C#)
Si usa `#define` per definire un simbolo. Quando si usa il simbolo come espressione passata alla direttiva [#if](./preprocessor-if.md), l'espressione restituisce `true`, come illustrato nell'esempio seguente:  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Non è possibile usare la direttiva `#define` per dichiarare valori costanti come in C e in C++. Le costanti in C# possono essere definite come membri statici di una classe o di uno struct. Se sono presenti più costanti di questo tipo, per usarle può essere utile creare una classe di costanti separata.  
  
 Per specificare le condizioni per la compilazione è possibile usare simboli. È possibile eseguire il test del simbolo tramite [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md). È anche possibile usare <xref:System.Diagnostics.ConditionalAttribute> per eseguire una compilazione condizionale.  
  
 È possibile definire un simbolo ma non è possibile assegnare a questo un valore. La direttiva `#define` deve essere inserita in un file prima di usare istruzioni che non siano anche direttive del preprocessore.  
  
 Un simbolo può anche essere definito tramite l'opzione del compilatore [-define](../compiler-options/define-compiler-option.md). Per rimuovere la definizione di un simbolo, è possibile usare [#undef](./preprocessor-undef.md).  
  
 Un simbolo definito tramite `-define` o `#define` non provoca conflitti con una variabile avente lo stesso nome. Il nome di una variabile, infatti, non può essere passato a una direttiva del preprocessore e un simbolo può essere valutato solo da una direttiva del preprocessore.  
  
 L'ambito di un simbolo creato tramite `#define` è il file in cui il simbolo è stato definito.  
  
 Come illustrato nell'esempio seguente, è necessario inserire direttive `#define` all'inizio del file.  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Per un esempio su come annullare la definizione di un simbolo, vedere [#undef](./preprocessor-undef.md).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Direttive per il preprocessore C#](./index.md)
- [const](../keywords/const.md)
- [Procedura: Compilare in modo condizionale con traccia e debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [#undef](./preprocessor-undef.md)
- [#if](./preprocessor-if.md)
