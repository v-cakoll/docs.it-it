---
title: Come analizzare le stringhe utilizzando String.Split (Guida di C
description: String.Split restituisce una matrice di stringhe divise da un set di delimitatori e rappresenta un modo semplice per analizzare le stringhe.
ms.date: 01/03/2018
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
ms.custom: mvc
ms.openlocfilehash: cf8307517213b54041b272843232eb595660b2e9
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389500"
---
# <a name="how-to-parse-strings-using-stringsplit-in-c"></a><span data-ttu-id="5dadd-104">Come analizzare le stringhe utilizzando String.Split in CHow to parse strings using String.Split in C\#</span><span class="sxs-lookup"><span data-stu-id="5dadd-104">How to parse strings using String.Split in C\#</span></span>

<span data-ttu-id="5dadd-105">Il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matrice di sottostringhe dividendo la stringa di input in base a uno o più delimitatori.</span><span class="sxs-lookup"><span data-stu-id="5dadd-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="5dadd-106">È spesso il modo più semplice per separare una stringa in corrispondenza della fine delle parole.</span><span class="sxs-lookup"><span data-stu-id="5dadd-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="5dadd-107">Questo metodo viene usato anche per dividere le stringhe in corrispondenza di altri caratteri o di altre stringhe specifiche.</span><span class="sxs-lookup"><span data-stu-id="5dadd-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="5dadd-108">Il codice seguente divide una frase comune in una matrice di stringhe per ogni parola.</span><span class="sxs-lookup"><span data-stu-id="5dadd-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="5dadd-109">Ogni istanza di un carattere separatore genera un valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="5dadd-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="5dadd-110">Caratteri separatori consecutivi generano una stringa vuota come valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="5dadd-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span> <span data-ttu-id="5dadd-111">È possibile vedere come viene creata una stringa vuota nell'esempio seguente, che usa il carattere spazio come separatore.</span><span class="sxs-lookup"><span data-stu-id="5dadd-111">You can see how an empty string is created in the following example, which uses the space character as a separator.</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="5dadd-112">Questo comportamento semplifica i formati, ad esempio i file con valori delimitati da virgole (CSV) che rappresentano dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="5dadd-112">This behavior makes it easier for formats like comma-separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="5dadd-113">Due virgole consecutive rappresentano una colonna vuota.</span><span class="sxs-lookup"><span data-stu-id="5dadd-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="5dadd-114">È possibile passare un parametro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> facoltativo per escludere tutte le stringhe vuote nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="5dadd-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="5dadd-115">Per un'elaborazione più complessa della raccolta restituita, è possibile modificare la sequenza di risultati tramite [LINQ](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="5dadd-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>

<span data-ttu-id="5dadd-116"><xref:System.String.Split%2A?displayProperty=nameWithType> può usare più caratteri separatori.</span><span class="sxs-lookup"><span data-stu-id="5dadd-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span>
<span data-ttu-id="5dadd-117">L'esempio seguente usa spazi, virgole, punti, due punti e tabulazioni, tutti passati a <xref:System.String.Split%2A> in una matrice contenente questi caratteri di separazione.</span><span class="sxs-lookup"><span data-stu-id="5dadd-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>
<span data-ttu-id="5dadd-118">Il ciclo nella parte inferiore del codice visualizza ogni parola nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="5dadd-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="5dadd-119">Istanze consecutive di un separatore generano una stringa vuota nella matrice di output:</span><span class="sxs-lookup"><span data-stu-id="5dadd-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="5dadd-120"><xref:System.String.Split%2A?displayProperty=nameWithType> può accettare una matrice di stringhe (sequenze di caratteri, anziché caratteri singoli, con la funzione di separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="5dadd-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="5dadd-121">È possibile provare questi esempi esaminando il codice nel repository [GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="5dadd-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="5dadd-122">Oppure è possibile scaricare gli esempi [come file ZIP](../../../samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="5dadd-122">Or you can download the samples [as a zip file](../../../samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="5dadd-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dadd-123">See also</span></span>

- [<span data-ttu-id="5dadd-124">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="5dadd-124">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="5dadd-125">Stringhe</span><span class="sxs-lookup"><span data-stu-id="5dadd-125">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="5dadd-126">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="5dadd-126">.NET Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)
