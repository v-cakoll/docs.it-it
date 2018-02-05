---
title: 'Procedura: Analizzare le stringhe con String.Split (guida a C#)'
description: String.Split restituisce una matrice di stringhe divise da un set di delimitatori e rappresenta un modo semplice per analizzare le stringhe.
ms.date: 01/03/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
author: BillWagner
ms.author: wiwagn
ms.custom: mvc
ms.openlocfilehash: 5143fed04148fb17697bd5d040ad23b762505db4
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2018
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a><span data-ttu-id="0ae84-104">Procedura: Analizzare le stringhe con String.Split (guida a C#)</span><span class="sxs-lookup"><span data-stu-id="0ae84-104">How to: Parse Strings Using String.Split (C# Guide)</span></span>

<span data-ttu-id="0ae84-105">Il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matrice di sottostringhe dividendo la stringa di input in base a uno o più delimitatori.</span><span class="sxs-lookup"><span data-stu-id="0ae84-105">The <xref:System.String.Split%2A?displayProperty=nameWithType> method creates an array of substrings by splitting the input string based on one or more delimiters.</span></span> <span data-ttu-id="0ae84-106">È spesso il modo più semplice per separare una stringa in corrispondenza della fine delle parole.</span><span class="sxs-lookup"><span data-stu-id="0ae84-106">It is often the easiest way to separate a string on word boundaries.</span></span> <span data-ttu-id="0ae84-107">Questo metodo viene usato anche per dividere le stringhe in corrispondenza di altri caratteri o di altre stringhe specifiche.</span><span class="sxs-lookup"><span data-stu-id="0ae84-107">It is also used to split strings on other specific characters or strings.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="0ae84-108">Il codice seguente divide una frase comune in una matrice di stringhe per ogni parola.</span><span class="sxs-lookup"><span data-stu-id="0ae84-108">The following code splits a common phrase into an array of strings for each word.</span></span>

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

<span data-ttu-id="0ae84-109">Ogni istanza di un carattere separatore genera un valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0ae84-109">Every instance of a separator character produces a value in the returned array.</span></span> <span data-ttu-id="0ae84-110">Caratteri separatori consecutivi generano una stringa vuota come valore nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0ae84-110">Consecutive separator characters produce the empty string as a value in the returned array.</span></span>  <span data-ttu-id="0ae84-111">Questo caso è illustrato nell'esempio seguente, che usa uno spazio come separatore:</span><span class="sxs-lookup"><span data-stu-id="0ae84-111">You can see this in the following example, which uses space as a separator:</span></span>

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

<span data-ttu-id="0ae84-112">Questo comportamento semplifica l'uso di alcuni formati, ad esempio dei file con valori delimitati da virgole (CSV, Comma Separated Value) che rappresentano dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="0ae84-112">This behavior makes it easier for formats like comma separated values (CSV) files representing tabular data.</span></span> <span data-ttu-id="0ae84-113">Due virgole consecutive rappresentano una colonna vuota.</span><span class="sxs-lookup"><span data-stu-id="0ae84-113">Consecutive commas represent a blank column.</span></span>

<span data-ttu-id="0ae84-114">È possibile passare un parametro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> facoltativo per escludere tutte le stringhe vuote nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0ae84-114">You can pass an optional <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> parameter to exclude any empty strings in the returned array.</span></span> <span data-ttu-id="0ae84-115">Per un'elaborazione più complessa della raccolta restituita, è possibile modificare la sequenza di risultati tramite [LINQ](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ae84-115">For more complicated processing of the returned collection, you can use [LINQ](../programming-guide/concepts/linq/index.md) to manipulate the result sequence.</span></span>    

<span data-ttu-id="0ae84-116"><xref:System.String.Split%2A?displayProperty=nameWithType> può usare più caratteri separatori.</span><span class="sxs-lookup"><span data-stu-id="0ae84-116"><xref:System.String.Split%2A?displayProperty=nameWithType> can use multiple separator characters.</span></span> <span data-ttu-id="0ae84-117">L'esempio seguente usa spazi, virgole, punti, due punti e tabulazioni, tutti passati a <xref:System.String.Split%2A> in una matrice contenente questi caratteri di separazione.</span><span class="sxs-lookup"><span data-stu-id="0ae84-117">The following example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters, to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="0ae84-118">Il ciclo nella parte inferiore del codice visualizza ogni parola nella matrice restituita.</span><span class="sxs-lookup"><span data-stu-id="0ae84-118">The loop at the bottom of the code displays each of the words in the returned array.</span></span>  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

<span data-ttu-id="0ae84-119">Istanze consecutive di un separatore generano una stringa vuota nella matrice di output:</span><span class="sxs-lookup"><span data-stu-id="0ae84-119">Consecutive instances of any separator produce the empty string in the output array:</span></span>

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<span data-ttu-id="0ae84-120"><xref:System.String.Split%2A?displayProperty=nameWithType> può accettare una matrice di stringhe (sequenze di caratteri, anziché caratteri singoli, con la funzione di separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="0ae84-120"><xref:System.String.Split%2A?displayProperty=nameWithType> can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

<span data-ttu-id="0ae84-121">È possibile provare questi esempi esaminando il codice nel [repository GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings)</span><span class="sxs-lookup"><span data-stu-id="0ae84-121">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings)</span></span>

## <a name="see-also"></a><span data-ttu-id="0ae84-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ae84-122">See Also</span></span>  
 [<span data-ttu-id="0ae84-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0ae84-123">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="0ae84-124">Stringhe</span><span class="sxs-lookup"><span data-stu-id="0ae84-124">Strings</span></span>](../programming-guide/strings/index.md)  
 [<span data-ttu-id="0ae84-125">Espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0ae84-125">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)
