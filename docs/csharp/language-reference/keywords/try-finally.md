---
title: try...finally - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- finally
- finally_CSharpKeyword
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
ms.openlocfilehash: 2c4c69b1e104aed968bc24bac690de83026643a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713014"
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

Per altre informazioni, vedere la sezione [Istruzione try](~/_csharplang/spec/statements.md#the-try-statement) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Istruzioni try, throw e catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [generazione](throw.md)
- [try-catch](try-catch.md)
- [Procedura: Come generare in modo esplicito le eccezioni](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
