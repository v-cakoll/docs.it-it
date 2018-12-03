---
title: string (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: 66b1729363878f69f868b8b8fd6e9e7011426f27
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672004"
---
# <a name="string-c-reference"></a>string (Riferimenti per C#)

Il tipo `string` rappresenta una sequenza di zero o più caratteri Unicode. `string` è un alias per <xref:System.String> in .NET.

Sebbene `string` sia un tipo riferimento, gli operatori di uguaglianza (`==` e `!=`) vengono definiti per confrontare i valori degli oggetti `string` e non dei riferimenti. In questo modo il test di uguaglianza delle stringhe è più intuitivo. Ad esempio:

```csharp
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine((object)a == (object)b);
```

Viene visualizzato "True" e quindi "False" perché il contenuto delle stringhe è equivalente, ma `a` e `b` non fanno riferimento alla stessa istanza della stringa.

L'operatore + concatena le stringhe:

```csharp
string a = "good " + "morning";
```

Questo crea un oggetto stringa contenente "good morning".

Le stringhe sono *immutabili*: non è possibile modificare il contenuto di un oggetto stringa dopo la creazione dell'oggetto, sebbene la sintassi sembri indicare che è possibile apportare modifiche. Ad esempio, quando si scrive il codice, il compilatore crea un nuovo oggetto stringa per archiviare la nuova sequenza di caratteri e il nuovo oggetto viene assegnato a b. La stringa "h" è quindi idonea per Garbage Collection.

```csharp
string b = "h";
b += "ello";
```

L'operatore [] può essere usato per accedere in lettura ai singoli caratteri di un `string`:

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

I valori letterali della stringa sono di tipo `string` e possono essere scritti in due formati, tra virgolette e @-quoted. I valori letterali della stringa tra virgolette sono racchiusi in virgolette doppie ("):

```csharp
"good morning"  // a string literal
```

I valori letterali della stringa possono contenere qualsiasi carattere letterale. Sono incluse le sequenze di escape. L'esempio seguente usa una sequenza di escape `\\` per la barra rovesciata, `\u0066` per la lettera f e `\n` per la nuova riga.

```csharp
string a = "\\\u0066\n";
Console.WriteLine(a);
```

> [!NOTE]
> Il codice di escape `\udddd` (dove `dddd` è un numero a quattro cifre) rappresenta il carattere Unicode U+`dddd`. Vengono riconosciuti anche i codici di escape Unicode a otto cifre: `\Udddddddd`.

I valori letterali della stringa verbatim iniziano con `@` e sono anche racchiusi tra virgolette doppie. Ad esempio:

```csharp
@"good morning"  // a string literal
```

Il vantaggio delle stringhe verbatim è che le sequenze di escape *non* sono elaborate, e quindi rendono più semplice scrivere, ad esempio, un nome completo del file:

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

Per includere le virgolette doppie in una stringa @-quoted, duplicarla:

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

Per altri usi del carattere speciale `@`, vedere [@ - identificatore verbatim](../tokens/verbatim.md).

Per altre informazioni sulle stringhe in C#, vedere [Stringhe](../../programming-guide/strings/index.md).

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#17)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Procedure consigliate per l'uso delle stringhe](../../../standard/base-types/best-practices-strings.md)
- [Parole chiave di C#](index.md)
- [Tipi riferimento](reference-types.md)
- [Tipi valore](value-types.md)
- [Operazioni di base su stringhe](../../../standard/base-types/basic-string-operations.md)
- [Creazione di nuove stringhe](../../../standard/base-types/creating-new.md)
- [Tabella di formattazione dei risultati numerici](formatting-numeric-results-table.md)
