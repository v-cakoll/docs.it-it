---
title: È possibile applicare l'attributo 'Extension' solo alle dichiarazioni 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 9b8f49c498699a8f7d1c4b329e82258501aa0c47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363098"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>È possibile applicare l'attributo 'Extension' solo alle dichiarazioni 'Module', 'Sub' o 'Function'

L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard. Il metodo di estensione può essere una `Sub` routine o una `Function` routine. Tutti i metodi di estensione devono essere contrassegnati con l'attributo extension, `<Extension()>` , dallo <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> spazio dei nomi. Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo. Nessun altro uso dell'attributo di estensione è valido.

**ID errore:** BC36550

## <a name="to-correct-this-error"></a>Per correggere l'errore

- Rimuovere l'attributo di estensione.

- Riprogettare l'estensione come metodo, definito in un modulo contenitore.

## <a name="example"></a>Esempio

Nell'esempio seguente viene definito un `Print` metodo per il `String` tipo di dati.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>Vedere anche

- [Panoramica degli attributi](../../programming-guide/concepts/attributes/index.md)
- [Metodi di estensione](../../programming-guide/language-features/procedures/extension-methods.md)
- [Istruzione Module](../statements/module-statement.md)
