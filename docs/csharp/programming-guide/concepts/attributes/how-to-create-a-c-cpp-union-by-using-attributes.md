---
title: Come creare un'unione C/C
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: ff8ce560444581a28b257820573224f89a274cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141579"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a>Come creare un'unione C/C

Utilizzando gli attributi, è possibile personalizzare il modo in cui gli struct vengono disposti in memoria. Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.

## <a name="example"></a>Esempio

In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestUnion
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public byte b;
}
```

## <a name="example"></a>Esempio

Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestExplicit
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public long lg;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i1;

    [System.Runtime.InteropServices.FieldOffset(4)]
    public int i2;

    [System.Runtime.InteropServices.FieldOffset(8)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(12)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(14)]
    public byte b;
}
```

I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`. Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.

## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guida per programmatori C#](../../index.md)
- [Attributi](../../../../standard/attributes/index.md)
- [Reflection (C#)](../reflection.md)
- [Attributi (C#)](index.md)
- [Creazione di attributi personalizzati (C#)](creating-custom-attributes.md)
- [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md) (Accesso agli attributi con reflection (C#))
