---
title: Analizzare le stringhe con String. Split (Guida a C#)
description: Il metodo Split restituisce una matrice di stringhe suddivise da un set di delimitatori. e rappresenta un modo semplice per analizzare le stringhe.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 7c5d8fa462775c6f3a9981693129997dda6c2286
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324146"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a>Come analizzare le stringhe con String. Split in C\#

Il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matrice di sottostringhe dividendo la stringa di input in base a uno o più delimitatori. Questo metodo è spesso il modo più semplice per separare una stringa sui limiti di parola. Viene usato anche per suddividere le stringhe in altri caratteri o stringhe specifiche.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Il codice seguente divide una frase comune in una matrice di stringhe per ogni parola.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

Ogni istanza di un carattere separatore genera un valore nella matrice restituita. Caratteri separatori consecutivi generano una stringa vuota come valore nella matrice restituita. È possibile vedere come viene creata una stringa vuota nell'esempio seguente, che usa il carattere spazio come separatore.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

Questo comportamento rende più semplice per i formati come i file con valori delimitati da virgole (CSV) che rappresentano dati tabulari. Due virgole consecutive rappresentano una colonna vuota.

È possibile passare un parametro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> facoltativo per escludere tutte le stringhe vuote nella matrice restituita. Per un'elaborazione più complessa della raccolta restituita, è possibile modificare la sequenza di risultati tramite [LINQ](../programming-guide/concepts/linq/index.md).

<xref:System.String.Split%2A?displayProperty=nameWithType> può usare più caratteri separatori.
Nell'esempio seguente vengono usati spazi, virgole, punti, due punti e tabulazioni come caratteri di separazione, che vengono passati a <xref:System.String.Split%2A> in una matrice.
Il ciclo nella parte inferiore del codice visualizza ogni parola nella matrice restituita.

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

Istanze consecutive di un separatore generano una stringa vuota nella matrice di output:

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<xref:System.String.Split%2A?displayProperty=nameWithType> può accettare una matrice di stringhe (sequenze di caratteri, anziché caratteri singoli, con la funzione di separatori per l'analisi della stringa di destinazione).

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../programming-guide/index.md)
- [Stringhe](../programming-guide/strings/index.md)
- [Espressioni regolari .NET](../../standard/base-types/regular-expressions.md)
