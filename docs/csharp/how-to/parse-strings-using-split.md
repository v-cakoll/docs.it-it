---
title: Come analizzare le stringhe con String. Split (Guida a C#)
description: String.Split restituisce una matrice di stringhe divise da un set di delimitatori e rappresenta un modo semplice per analizzare le stringhe.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: 4f0056426fb29ec3d76093e57fa45e2046f27a4f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662992"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="23287-104">Come analizzare le stringhe con String. Split in C\#</span><span class="sxs-lookup"><span data-stu-id="23287-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="23287-105">Il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matrice di sottostringhe dividendo la stringa di input in base a uno o più delimitatori.</span><span class="sxs-lookup"><span data-stu-id="23287-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="23287-106">È spesso il modo più semplice per separare una stringa in corrispondenza della fine delle parole.</span><span class="sxs-lookup"><span data-stu-id="23287-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="23287-107">Questo metodo viene usato anche per dividere le stringhe in corrispondenza di altri caratteri o di altre stringhe specifiche.</span><span class="sxs-lookup"><span data-stu-id="23287-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="23287-108">Il codice seguente divide una frase comune in una matrice di stringhe per ogni parola.</span><span class="sxs-lookup"><span data-stu-id="23287-108">The following code splits a common phrase into an array of strings for each word.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet1":::

<span data-ttu-id="23287-109">Ogni istanza di un carattere separatore genera un valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="23287-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="23287-110">Caratteri separatori consecutivi generano una stringa vuota come valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="23287-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="23287-111">È possibile vedere come viene creata una stringa vuota nell'esempio seguente, che usa il carattere spazio come separatore.</span><span class="sxs-lookup"><span data-stu-id="23287-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet2":::

<span data-ttu-id="23287-112">Questo comportamento rende più semplice per i formati come i file con valori delimitati da virgole (CSV) che rappresentano dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="23287-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="23287-113">Due virgole consecutive rappresentano una colonna vuota.</span><span class="sxs-lookup"><span data-stu-id="23287-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="23287-114">È possibile passare un parametro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> facoltativo per escludere tutte le stringhe vuote nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="23287-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="23287-115">Per un'elaborazione più complessa della raccolta restituita, è possibile modificare la sequenza di risultati tramite [LINQ](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="23287-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="23287-116"><xref:System.String.Split%2A?displayProperty=nameWithType> può usare più caratteri separatori.</span><span class="sxs-lookup"><span data-stu-id="23287-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="23287-117">L'esempio seguente usa spazi, virgole, punti, due punti e tabulazioni, tutti passati a <xref:System.String.Split%2A> in una matrice contenente questi caratteri di separazione.</span><span class="sxs-lookup"><span data-stu-id="23287-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="23287-118">Il ciclo nella parte inferiore del codice visualizza ogni parola nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="23287-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet3":::

<span data-ttu-id="23287-119">Istanze consecutive di un separatore generano una stringa vuota nella matrice di output:</span><span class="sxs-lookup"><span data-stu-id="23287-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet4":::

<span data-ttu-id="23287-120"><xref:System.String.Split%2A?displayProperty=nameWithType> può accettare una matrice di stringhe (sequenze di caratteri, anziché caratteri singoli, con la funzione di separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="23287-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs" id="Snippet5":::

## <a name="see-also"></a><span data-ttu-id="23287-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23287-121">See also</span></span>

- [<span data-ttu-id="23287-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="23287-122">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="23287-123">Stringhe</span><span class="sxs-lookup"><span data-stu-id="23287-123">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="23287-124">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="23287-124">.NET regular expressions</span></span>](../../standard/base-types/regular-expressions.md)
