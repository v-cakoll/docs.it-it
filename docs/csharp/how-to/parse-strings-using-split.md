---
title: 'Procedura: Analizzare le stringhe con String.Split (Guida a C#)'
description: String.Split restituisce una matrice di stringhe divise da un set di delimitatori e rappresenta un modo semplice per analizzare le stringhe.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: a8cb3a62497379f60e9cc6dec3d342192361f865
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603720"
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="c106e-104">Procedura: Analizzare le stringhe con String.Split (Guida a C#)</span><span class="sxs-lookup"><span data-stu-id="c106e-104">How to: Parse Strings Using String.Split (C# Guide)</span></span>

<span data-ttu-id="c106e-105">Il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matrice di sottostringhe dividendo la stringa di input in base a uno o più delimitatori.</span><span class="sxs-lookup"><span data-stu-id="c106e-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="c106e-106">È spesso il modo più semplice per separare una stringa in corrispondenza della fine delle parole.</span><span class="sxs-lookup"><span data-stu-id="c106e-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="c106e-107">Questo metodo viene usato anche per dividere le stringhe in corrispondenza di altri caratteri o di altre stringhe specifiche.</span><span class="sxs-lookup"><span data-stu-id="c106e-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="c106e-108">Il codice seguente divide una frase comune in una matrice di stringhe per ogni parola.</span><span class="sxs-lookup"><span data-stu-id="c106e-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="c106e-109">Ogni istanza di un carattere separatore genera un valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="c106e-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="c106e-110">Caratteri separatori consecutivi generano una stringa vuota come valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="c106e-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="c106e-111">Questo caso è illustrato nell'esempio seguente, che usa uno spazio come separatore:</span><span class="sxs-lookup"><span data-stu-id="c106e-111">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="c106e-112">Questo comportamento semplifica l'uso di alcuni formati, ad esempio dei file con valori delimitati da virgole (CSV, Comma Separated Value) che rappresentano dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="c106e-112">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="c106e-113">Due virgole consecutive rappresentano una colonna vuota.</span><span class="sxs-lookup"><span data-stu-id="c106e-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="c106e-114">È possibile passare un parametro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> facoltativo per escludere tutte le stringhe vuote nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="c106e-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="c106e-115">Per un'elaborazione più complessa della raccolta restituita, è possibile modificare la sequenza di risultati tramite [LINQ](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="c106e-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="c106e-116"><xref:System.String.Split%2A?displayProperty=nameWithType> può usare più caratteri separatori.</span><span class="sxs-lookup"><span data-stu-id="c106e-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="c106e-117">L'esempio seguente usa spazi, virgole, punti, due punti e tabulazioni, tutti passati a <xref:System.String.Split%2A> in una matrice contenente questi caratteri di separazione.</span><span class="sxs-lookup"><span data-stu-id="c106e-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="c106e-118">Il ciclo nella parte inferiore del codice visualizza ogni parola nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="c106e-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="c106e-119">Istanze consecutive di un separatore generano una stringa vuota nella matrice di output:</span><span class="sxs-lookup"><span data-stu-id="c106e-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="c106e-120"><xref:System.String.Split%2A?displayProperty=nameWithType> può accettare una matrice di stringhe (sequenze di caratteri, anziché caratteri singoli, con la funzione di separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="c106e-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="c106e-121">È possibile provare questi esempi esaminando il codice nel [repository GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="c106e-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="c106e-122">Oppure è possibile scaricare gli esempi [come file ZIP](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="c106e-122">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="c106e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c106e-123">See also</span></span>

- [<span data-ttu-id="c106e-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c106e-124">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="c106e-125">Stringhe</span><span class="sxs-lookup"><span data-stu-id="c106e-125">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="c106e-126">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="c106e-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)
