---
ms.openlocfilehash: f131933f3cf7890939854c46f115e8deb8da1cc2
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888170"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="46c88-101">StringInfo e TextElementEnumerator sono ora conformi a UAX29</span><span class="sxs-lookup"><span data-stu-id="46c88-101">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="46c88-102">Prima di questa <xref:System.Globalization.StringInfo?displayProperty=fullName> <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> modifica, e non gestito correttamente tutti i cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="46c88-102">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="46c88-103">Alcuni grafemi sono stati divisi nelle loro componenti costituenti invece di essere tenuti insieme.</span><span class="sxs-lookup"><span data-stu-id="46c88-103">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="46c88-104">A <xref:System.Globalization.StringInfo> questo <xref:System.Globalization.TextElementEnumerator> punto, ed elaborare i cluster di grafemi in base all'ultima versione dello standard Unicode.</span><span class="sxs-lookup"><span data-stu-id="46c88-104">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="46c88-105">Inoltre, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo, che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="46c88-105">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="46c88-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="46c88-106">Change description</span></span>

<span data-ttu-id="46c88-107">Un cluster di [grafemi](https://www.unicode.org/glossary/#grapheme) o [grafemi esteso](https://www.unicode.org/glossary/#extended_grapheme_cluster) è un singolo carattere percepito dall'utente che può essere costituito da più punti di codice Unicode.</span><span class="sxs-lookup"><span data-stu-id="46c88-107">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="46c88-108">Ad esempio, la stringa contenente il carattere tailandese "kam" (:::no-loc text="กำ":::) è costituita dai due caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="46c88-108">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="46c88-109">:::no-loc text="ก":::('u0e01') THAI CHARACTER KO KAI</span><span class="sxs-lookup"><span data-stu-id="46c88-109">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="46c88-110">:::no-loc text=" ำ":::(Sezione : ''u0e33'') THAI CHARACTER SARA AM</span><span class="sxs-lookup"><span data-stu-id="46c88-110">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="46c88-111">Quando viene visualizzato all'utente, il sistema operativo combina i due caratteri per formare il :::no-loc text="กำ":::singolo carattere di visualizzazione (o grafema) "kam" o .</span><span class="sxs-lookup"><span data-stu-id="46c88-111">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="46c88-112">Le emoji possono anche essere costituite da più caratteri combinati per la visualizzazione in modo simile.</span><span class="sxs-lookup"><span data-stu-id="46c88-112">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="46c88-113">La documentazione di .NET a volte utilizza il termine "elemento di testo" quando si fa riferimento a un grafema.</span><span class="sxs-lookup"><span data-stu-id="46c88-113">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="46c88-114">Le <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> classi e esaminano le stringhe e restituiscono informazioni sui grafemi che contengono.</span><span class="sxs-lookup"><span data-stu-id="46c88-114">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="46c88-115">In .NET Framework (tutte le versioni) e .NET Core 3.x e versioni precedenti, queste due classi utilizzano la logica personalizzata che gestisce alcune classi di combinazione ma non sono completamente conformi allo [standard Unicode](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span><span class="sxs-lookup"><span data-stu-id="46c88-115">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="46c88-116">Ad esempio, <xref:System.Globalization.StringInfo> <xref:System.Globalization.TextElementEnumerator> le classi e suddividono erroneamente il singolo carattere tailandese "kam" nei relativi componenti costitutivi anziché tenerli insieme.</span><span class="sxs-lookup"><span data-stu-id="46c88-116">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="46c88-117">Queste classi anche erroneamente diviso il carattere emoji "🤷🏽 ♀️" in quattro gruppi (persona che shrugging, modificatore di tono della pelle, modificatore di genere, e un combinatore invisibile) invece di tenerli insieme come un singolo cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="46c88-117">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="46c88-118">A partire da .NET 5, le <xref:System.Globalization.StringInfo> classi e <xref:System.Globalization.TextElementEnumerator> implementano lo standard Unicode come definito da Unicode Standard [Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span><span class="sxs-lookup"><span data-stu-id="46c88-118">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="46c88-119">In particolare, ora restituiscono cluster di [grafemi estesi](https://www.unicode.org/glossary/#extended_grapheme_cluster) per tutte le classi combinate.</span><span class="sxs-lookup"><span data-stu-id="46c88-119">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="46c88-120">Si consideri il seguente codice in C:</span><span class="sxs-lookup"><span data-stu-id="46c88-120">Consider the following C# code:</span></span>

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

<span data-ttu-id="46c88-121">In .NET Framework e .NET Core 3.x e versioni precedenti, i grafemi vengono suddivisi e l'output della console è il seguente:</span><span class="sxs-lookup"><span data-stu-id="46c88-121">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

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

<span data-ttu-id="46c88-122">In .NET 5 e versioni successive, i grafemi vengono mantenuti insieme e l'output della console è il seguente:</span><span class="sxs-lookup"><span data-stu-id="46c88-122">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="46c88-123">Inoltre, a partire da .NET 5, il <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> metodo , che inverte i caratteri in una stringa in Visual Basic, ora segue anche lo standard Unicode per i cluster di grafemi.</span><span class="sxs-lookup"><span data-stu-id="46c88-123">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="46c88-124">Queste modifiche fanno parte di un set più ampio di miglioramenti Unicode e UTF-8 in .NET, tra cui un'API di <xref:System.Text.Rune?displayProperty=fullName> enumerazione del cluster grapheme estesa per completare le API di enumerazione del valore scalare Unicode introdotte con il tipo in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="46c88-124">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="46c88-125">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="46c88-125">Version introduced</span></span>

<span data-ttu-id="46c88-126">Anteprima 1 di .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="46c88-126">.NET 5.0 Preview 1</span></span>

### <a name="recommended-action"></a><span data-ttu-id="46c88-127">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="46c88-127">Recommended action</span></span>

<span data-ttu-id="46c88-128">Non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="46c88-128">You don't need to take any action.</span></span> <span data-ttu-id="46c88-129">Le app si comporterà automaticamente in modo più conforme agli standard in una varietà di scenari correlati alla globalizzazione.</span><span class="sxs-lookup"><span data-stu-id="46c88-129">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

### <a name="category"></a><span data-ttu-id="46c88-130">Category</span><span class="sxs-lookup"><span data-stu-id="46c88-130">Category</span></span>

<span data-ttu-id="46c88-131">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="46c88-131">Globalization</span></span>

### <a name="affected-apis"></a><span data-ttu-id="46c88-132">API interessate</span><span class="sxs-lookup"><span data-stu-id="46c88-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
