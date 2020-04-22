---
ms.openlocfilehash: 843c78bb4e4f88d9ac58308a91ab8278364c9580
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021629"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="95b58-101">.NET Core 3.0 segue le procedure consigliate di Unicode quando si sostituiscono sequenze di byte UTF-8 in formato non corretto</span><span class="sxs-lookup"><span data-stu-id="95b58-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="95b58-102">Quando <xref:System.Text.UTF8Encoding> la classe rileva una sequenza di byte UTF-8 in formato non corretto durante un'operazione di transcodifica byte-carattere, sostituirà tale sequenza con un carattere ' ' (U -FFFD REPLACEMENT CHARACTER) nella stringa di output.</span><span class="sxs-lookup"><span data-stu-id="95b58-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="95b58-103">.NET Core 3.0 differisce dalle versioni precedenti di .NET Core e .NET Framework seguendo le procedure consigliate Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.</span><span class="sxs-lookup"><span data-stu-id="95b58-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="95b58-104">Questo fa parte di uno sforzo più ampio per migliorare <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> la <xref:System.Text.Rune?displayProperty=nameWithType> gestione UTF-8 in tutta .NET, anche dai nuovi e tipi.</span><span class="sxs-lookup"><span data-stu-id="95b58-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="95b58-105">Al <xref:System.Text.UTF8Encoding> tipo è stato fornito meccanismi di gestione degli errori migliorati in modo che produca output coerente con i tipi appena introdotti.</span><span class="sxs-lookup"><span data-stu-id="95b58-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="95b58-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="95b58-106">Change description</span></span>

<span data-ttu-id="95b58-107">A partire da .NET Core 3.0, durante <xref:System.Text.UTF8Encoding> la transcodifica di byte in caratteri, la classe esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode.Starting with .NET Core 3.0, when transcoding bytes to characters, the class performs character substitution based on Unicode best practices.</span><span class="sxs-lookup"><span data-stu-id="95b58-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="95b58-108">Il meccanismo di sostituzione utilizzato è descritto da [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione denominato _Sostituzione U-FFFD delle sottoparti maximal_.</span><span class="sxs-lookup"><span data-stu-id="95b58-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="95b58-109">Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="95b58-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="95b58-110">Inoltre, se <xref:System.Text.UTF8Encoding> l'istanza è `throwOnInvalidBytes: true` stata costruita con (vedere<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>la `UTF8Encoding` [documentazione del costruttore UTF8Encoding]( , l'istanza continuerà a generare un input non valido anziché eseguire la sostituzione di U-FFFD.</span><span class="sxs-lookup"><span data-stu-id="95b58-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="95b58-111">Di seguito viene illustrato l'impatto di questa modifica con un input a 3 byte non valido:</span><span class="sxs-lookup"><span data-stu-id="95b58-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="95b58-112">Input a 3 byte in formato non corretto</span><span class="sxs-lookup"><span data-stu-id="95b58-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="95b58-113">Output prima di .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="95b58-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="95b58-114">Output che inizia con .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="95b58-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="95b58-115">`[ FFFD FFFD ]`(uscita a 2 caratteri)</span><span class="sxs-lookup"><span data-stu-id="95b58-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="95b58-116">`[ FFFD FFFD FFFD ]`(uscita a 3 caratteri)</span><span class="sxs-lookup"><span data-stu-id="95b58-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="95b58-117">Questo output di 3 caratteri è l'output preferito, secondo la _tabella 3-9_ del PDF Standard Unicode precedentemente collegato.</span><span class="sxs-lookup"><span data-stu-id="95b58-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95b58-118">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="95b58-118">Version introduced</span></span>

<span data-ttu-id="95b58-119">3.0</span><span class="sxs-lookup"><span data-stu-id="95b58-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95b58-120">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="95b58-120">Recommended action</span></span>

<span data-ttu-id="95b58-121">Non è richiesta alcuna azione da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="95b58-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="95b58-122">Category</span><span class="sxs-lookup"><span data-stu-id="95b58-122">Category</span></span>

<span data-ttu-id="95b58-123">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="95b58-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95b58-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="95b58-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
