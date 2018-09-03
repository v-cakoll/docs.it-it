---
title: Parola chiave const (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: f586b6d097a8592fd74e92df7886b519d623e478
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393005"
---
# <a name="const-c-reference"></a>const (Riferimenti per C#)

Si usa la parola chiave `const` per dichiarare un campo costante o una variabile locale costante. I campi e le variabili locali costanti non sono variabili e non sono quindi modificabili. Gli elementi costanti possono essere numeri, valori booleani, stringhe o un riferimento Null. Non creare una costante per rappresentare informazioni di cui si prevede la modifica in qualsiasi momento. Un campo costante, ad esempio, non deve essere usato per archiviare il prezzo di un servizio, il numero di versione di un prodotto o il nome dell'organizzazione di una società. Tali valori potrebbero cambiare nel tempo e, poiché i compilatori propagano le costanti, eventuale altro codice compilato con quelle librerie dovrebbe essere ricompilato per riflettere le modifiche. Vedere anche la parola chiave [readonly](../../../csharp/language-reference/keywords/readonly.md). Ad esempio:

```csharp
const int x = 0;
public const double gravitationalConstant = 6.673e-11;
private const string productName = "Visual C#";
```

## <a name="remarks"></a>Note

Il tipo di una dichiarazione di costante specifica il tipo di membri introdotti dalla dichiarazione. L'inizializzatore di una variabile locale costante o di un campo costante deve essere un'espressione costante che possa essere convertita in modo implicito nel tipo di destinazione.

Un'espressione di costanti è un'espressione che può essere valutata interamente in fase di compilazione. Di conseguenza, gli unici valori possibili per le costanti dei tipi di riferimento sono `string` e il riferimento Null.

La dichiarazione di costante può includere più costanti, ad esempio:

```csharp
public const double x = 1.0, y = 2.0, z = 3.0;
```

Il modificatore `static` non è consentito in una dichiarazione di costante.

Una costante può far parte di un'espressione costante, ad esempio:

```csharp
public const int c1 = 5;
public const int c2 = c1 + 100;
```

> [!NOTE]
> La parola chiave [readonly](../../../csharp/language-reference/keywords/readonly.md) è diversa dalla parola chiave `const`. Un campo `const` può essere inizializzato solo nella dichiarazione del campo. Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore. I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato. Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nella riga seguente: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Esempio

In questo esempio viene illustrato come usare le costanti come variabili locali.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
- [readonly](../../../csharp/language-reference/keywords/readonly.md)
