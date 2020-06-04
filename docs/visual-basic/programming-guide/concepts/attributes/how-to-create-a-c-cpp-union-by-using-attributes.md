---
title: "Procedura: creare un'Unione C-C + + tramite attributi"
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: ebab0ad947f776932f9379af3969e369eeec1941
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400681"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Procedura: Creare un'unione C/C++ tramite attributi (Visual Basic)

L'uso degli attributi consente di personalizzare la disposizione degli struct in memoria. Ad esempio, tramite gli attributi `StructLayout(LayoutKind.Explicit)` e `FieldOffset` è possibile creare una struttura che in C/C++ è nota come unione.

## <a name="example"></a>Esempio

In questo segmento di codice tutti i campi di `TestUnion` iniziano in corrispondenza della stessa posizione di memoria.

```vb
' Add an Imports statement for System.Runtime.InteropServices.

<System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestUnion
    <System.Runtime.InteropServices.FieldOffset(0)>
    Public i As Integer

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public d As Double

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public c As Char

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public b As Byte
End Structure
```

## <a name="example"></a>Esempio

Nell'esempio seguente i campi iniziano in corrispondenza di posizioni diverse impostate in modo esplicito.

```vb
' Add an Imports statement for System.Runtime.InteropServices.

 <System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestExplicit
     <System.Runtime.InteropServices.FieldOffset(0)>
     Public lg As Long

     <System.Runtime.InteropServices.FieldOffset(0)>
     Public i1 As Integer

     <System.Runtime.InteropServices.FieldOffset(4)>
     Public i2 As Integer

     <System.Runtime.InteropServices.FieldOffset(8)>
     Public d As Double

     <System.Runtime.InteropServices.FieldOffset(12)>
     Public c As Char

     <System.Runtime.InteropServices.FieldOffset(14)>
     Public b As Byte
 End Structure
```

I due campi integer, `i1` e `i2`, condividono le stesse posizioni di memoria di `lg`. Questo tipo di controllo sul layout degli struct è utile quando si usa la chiamata di piattaforma.

## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guida per programmatori Visual Basic](../../index.md)
- [Attributi](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../reflection.md)
- [Attributi (Visual Basic)](../../../language-reference/attributes.md)
- [Creazione di attributi personalizzati (Visual Basic)](creating-custom-attributes.md)
- [Accesso agli attributi tramite reflection (Visual Basic)](accessing-attributes-by-using-reflection.md)
