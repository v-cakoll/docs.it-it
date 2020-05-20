---
ms.openlocfilehash: c0c1c9c9d8e3aeb6f689f754d09b50b208b54112
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702265"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="9f507-101">StringInfo e TextElementEnumerator ora sono conformi a UAX29</span><span class="sxs-lookup"><span data-stu-id="9f507-101">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="9f507-102">Prima di questa modifica, <xref:System.Globalization.StringInfo?displayProperty=fullName> non venivano <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> gestiti correttamente tutti i cluster grafema.</span><span class="sxs-lookup"><span data-stu-id="9f507-102">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="9f507-103">Alcuni grafemi sono stati suddivisi in componenti costitutivi anziché essere mantenuti insieme.</span><span class="sxs-lookup"><span data-stu-id="9f507-103">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="9f507-104">A questo punto, <xref:System.Globalization.StringInfo> ed <xref:System.Globalization.TextElementEnumerator> elabora i cluster grafema in base alla versione più recente dello standard Unicode.</span><span class="sxs-lookup"><span data-stu-id="9f507-104">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="9f507-105">Inoltre, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster grafema.</span><span class="sxs-lookup"><span data-stu-id="9f507-105">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9f507-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="9f507-106">Change description</span></span>

<span data-ttu-id="9f507-107">Un cluster [grafema](https://www.unicode.org/glossary/#grapheme) o [grafema esteso](https://www.unicode.org/glossary/#extended_grapheme_cluster) è un singolo carattere percepito dall'utente che può essere costituito da più punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="9f507-107">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="9f507-108">Ad esempio, la stringa contenente il carattere tailandese "Kam" ( :::no-loc text="กำ"::: ) è costituita dai due caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f507-108">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="9f507-109">:::no-loc text="ก":::(=' \u0e01') CARATTERE TAILANDESE KO KAI</span><span class="sxs-lookup"><span data-stu-id="9f507-109">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="9f507-110">:::no-loc text=" ำ":::(=' \u0e33') CARATTERE TAILANDESE SARA AM</span><span class="sxs-lookup"><span data-stu-id="9f507-110">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="9f507-111">Quando viene visualizzato all'utente, il sistema operativo combina i due caratteri per formare il singolo carattere di visualizzazione (o grafema) "Kam" o :::no-loc text="กำ"::: .</span><span class="sxs-lookup"><span data-stu-id="9f507-111">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="9f507-112">Emoji può anche essere costituito da più caratteri combinati per la visualizzazione in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="9f507-112">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="9f507-113">La documentazione di .NET usa talvolta il termine "elemento di testo" quando si fa riferimento a un grafema.</span><span class="sxs-lookup"><span data-stu-id="9f507-113">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="9f507-114">Le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e controllano le stringhe e restituiscono informazioni sui grafemi in essi contenute.</span><span class="sxs-lookup"><span data-stu-id="9f507-114">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="9f507-115">In .NET Framework (tutte le versioni) e .NET Core 3. x e versioni precedenti, queste due classi usano la logica personalizzata che gestisce alcune classi combinate, ma non è completamente conforme allo [standard Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span><span class="sxs-lookup"><span data-stu-id="9f507-115">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="9f507-116">Ad esempio, le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e suddividono erroneamente il singolo carattere tailandese "Kam" nei componenti costitutivi anziché mantenerli insieme.</span><span class="sxs-lookup"><span data-stu-id="9f507-116">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="9f507-117">Queste classi, inoltre, suddividono erroneamente il carattere emoji "🤷🏽 ♀️" in quattro cluster (disattivazione della persona, modificatore di tono della pelle, modificatore Gender e un combinatore invisibile) invece di mantenerli insieme come singolo cluster grafema.</span><span class="sxs-lookup"><span data-stu-id="9f507-117">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="9f507-118">A partire da .NET 5, <xref:System.Globalization.StringInfo> le <xref:System.Globalization.TextElementEnumerator> classi e implementano lo standard Unicode come definito da [Unicode Standard Annex \# 29, Rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span><span class="sxs-lookup"><span data-stu-id="9f507-118">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="9f507-119">In particolare, ora restituiscono [cluster grafema estesi](https://www.unicode.org/glossary/#extended_grapheme_cluster) per tutte le classi combinate.</span><span class="sxs-lookup"><span data-stu-id="9f507-119">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="9f507-120">Si consideri il codice C# seguente:</span><span class="sxs-lookup"><span data-stu-id="9f507-120">Consider the following C# code:</span></span>

```cs
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="9f507-121">In .NET Framework e .NET Core 3. x e versioni precedenti, i grafemi vengono suddivisi e l'output della console è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9f507-121">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="9f507-122">In .NET 5 e versioni successive, i grafemi vengono mantenuti insieme e l'output della console è il seguente:</span><span class="sxs-lookup"><span data-stu-id="9f507-122">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="9f507-123">Inoltre, a partire da .NET 5, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster grafema.</span><span class="sxs-lookup"><span data-stu-id="9f507-123">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="9f507-124">Queste modifiche fanno parte di un set più ampio di miglioramenti Unicode e UTF-8 in .NET, inclusa un'API di enumerazione del cluster grafema estesa per completare le API di enumerazione dei valori scalari Unicode introdotte con il <xref:System.Text.Rune?displayProperty=fullName> tipo in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="9f507-124">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f507-125">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="9f507-125">Version introduced</span></span>

<span data-ttu-id="9f507-126">.NET 5,0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="9f507-126">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f507-127">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="9f507-127">Recommended action</span></span>

<span data-ttu-id="9f507-128">Non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="9f507-128">You don't need to take any action.</span></span> <span data-ttu-id="9f507-129">Le tue app si comporteranno automaticamente in modo più conforme agli standard in un'ampia gamma di scenari correlati alla globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f507-129">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

#### <a name="category"></a><span data-ttu-id="9f507-130">Category</span><span class="sxs-lookup"><span data-stu-id="9f507-130">Category</span></span>

<span data-ttu-id="9f507-131">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="9f507-131">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f507-132">API interessate</span><span class="sxs-lookup"><span data-stu-id="9f507-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
