---
title: Creazione di attributi personalizzati
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400694"
---
# <a name="creating-custom-attributes-visual-basic"></a>Creazione di attributi personalizzati (Visual Basic)

È possibile creare attributi personalizzati definendo una classe Attribute, ovvero una classe che deriva direttamente o indirettamente da <xref:System.Attribute>, la quale semplifica e rende più rapida l'identificazione delle definizioni degli attributi nei metadati. Si supponga di voler contrassegnare i tipi con il nome del programmatore che ha scritto il tipo. Si potrebbe definire una classe Attribute `Author` personalizzata:

```vb
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName
        version = 1.0
    End Sub
End Class
```

Il nome della classe è il nome dell'attributo, `Author`. La classe deriva da `System.Attribute`, quindi è una classe Attribute personalizzata. I parametri del costruttore sono parametri posizionali dell'attributo personalizzato. In questo esempio `name` è un parametro posizionale. Tutte le proprietà o i campi pubblici di lettura/scrittura sono parametri denominati. In questo caso `version` è l'unico parametro denominato. Si noti l'uso dell'attributo `AttributeUsage` per rendere l'attributo `Author` valido solo per la classe e le dichiarazioni `Structure`.

È possibile usare questo nuovo attributo come indicato di seguito:

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

`AttributeUsage` ha un parametro denominato, `AllowMultiple`, che consente di rendere un attributo personalizzato monouso o multiuso. Nell'esempio di codice seguente viene creato un attributo multiuso.

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

Nell'esempio vengono applicati a una classe più attributi dello stesso tipo.

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> Se la classe Attribute contiene una proprietà, tale proprietà deve essere di lettura/scrittura.

## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection>
- [Guida per programmatori Visual Basic](../../index.md)
- [Scrittura di attributi personalizzati](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflection (Visual Basic)](../reflection.md)
- [Attributi (Visual Basic)](../../../language-reference/attributes.md)
- [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)
- [AttributeUsage (Visual Basic)](attributeusage.md)
