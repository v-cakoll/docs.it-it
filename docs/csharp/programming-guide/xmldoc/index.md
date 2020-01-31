---
title: Commenti in formato documentazione C# XML-Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: f5a507bc35b0cc0a679fd055bfc255bb3cb9a090
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789790"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Commenti relativi alla documentazioneC# XML (Guida per programmatori)

In C#è possibile creare la documentazione per il codice includendo elementi XML in campi di commento speciali (indicati da barre triple) nel codice sorgente direttamente prima del blocco di codice a cui fanno riferimento i commenti, ad esempio.

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

Quando si esegue la compilazione con l'opzione [-doc](../../language-reference/compiler-options/doc-compiler-option.md) , il compilatore cerca tutti i tag XML nel codice sorgente e crea un file di documentazione XML. Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).

Per fare riferimento agli elementi XML (ad esempio, la funzione elabora elementi XML specifici che si desidera descrivere in un commento della documentazione XML), è possibile utilizzare il meccanismo standard (`<` e `>`).  Per fare riferimento agli identificatori generici in elementi di riferimento di codice (`cref`), è possibile usare caratteri di escape, ad esempio `cref="List&lt;T&gt;"`, o parentesi graffe (`cref="List{T}"`).  Come caso particolare, il compilatore analizza le parentesi graffe come parentesi uncinate per rendere il commento relativo alla documentazione meno complesso da creare quando viene fatto riferimento a identificatori generici.

> [!NOTE]
> I commenti relativi alla documentazione XML non sono metadati, ovvero non vengono inclusi nell'assembly compilato e pertanto non sono accessibili mediante reflection.

## <a name="in-this-section"></a>In questa sezione

- [Tag consigliati per i commenti relativi alla documentazione](./recommended-tags-for-documentation-comments.md)

- [Elaborazione del file XML](./processing-the-xml-file.md)

- [Delimitatori per i tag della documentazione](./delimiters-for-documentation-tags.md)

- [Come utilizzare le funzionalità della documentazione XML](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a>Sezioni correlate

Per altre informazioni, vedere:

- [-DOC (elabora i commenti relativi alla documentazione)](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
