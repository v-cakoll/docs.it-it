---
title: try...finally - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: e8442438d06e8853e159b717b1f86fdce5c4b8f7
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422152"
---
# <a name="try-finally-c-reference"></a>try...finally (Riferimenti per C#)

Usando un blocco `finally`, è possibile eliminare le risorse allocate in un blocco [try](try-catch.md) ed è possibile eseguire codice anche se viene generata un'eccezione di blocco `try`. In genere, le istruzioni di un blocco `finally` vengono eseguite quando il controllo lascia un'istruzione `try`. Il trasferimento del controllo può verificarsi come risultato dell'esecuzione normale, dell'esecuzione di un'istruzione `break`, `continue`, `goto` o `return` o della propagazione di un'eccezione dell'istruzione `try`.

All'interno di un'eccezione gestita, l'esecuzione del blocco `finally` associato è garantita. Tuttavia, se l'eccezione non è gestita, l'esecuzione del blocco `finally` dipende da come viene attivata l'operazione di rimozione dell'eccezione. Ciò, a sua volta, dipende da come viene configurato il computer.

In genere, quando un'eccezione non gestita termina un'applicazione non è importante sapere se il blocco `finally` è in esecuzione. Tuttavia, se si dispone di istruzioni in un blocco `finally` che deve essere eseguito anche in questo caso, una soluzione consiste nell'aggiungere un blocco `catch` all'istruzione `try`-`finally`. In alternativa, è possibile intercettare l'eccezione che potrebbe essere generata nel blocco `try` di un'istruzione `try`-`finally` in alto nello stack di chiamate. Vale a dire, è possibile intercettare l'eccezione nel metodo che chiama il metodo che contiene l'istruzione `try`-`finally`, nel metodo che chiama questo metodo o in qualsiasi metodo nello stack di chiamate. Se non viene rilevata l'eccezione, l'esecuzione del blocco `finally` varia a seconda che il sistema operativo scelga di generare un'operazione di rimozione dell'eccezione o meno.

## <a name="example"></a>Esempio

Nell'esempio seguente un'istruzione di conversione non valida causa un'eccezione `System.InvalidCastException`. L'eccezione viene non è gestita.

[!code-csharp[csrefKeywordsExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#4)]

Nell'esempio seguente viene intercettata un'eccezione del metodo `TryCast` in un metodo nella parte più in alto dello stack di chiamate.

[!code-csharp[csrefKeywordsExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#6)]

Per altre informazioni su `finally`, vedere [try-catch-finally](try-catch-finally.md).

C# contiene anche l'[istruzione using](using-statement.md), che fornisce funzionalità simili per gli oggetti <xref:System.IDisposable> con una sintassi comoda.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzioni try, throw e catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [throw](throw.md)
- [try-catch](try-catch.md)
- [Procedura: Generare in modo esplicito le eccezioni](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
