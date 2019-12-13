---
ms.openlocfilehash: db1d09c8c9e606b5327a42977a74a74703282d84
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568211"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a><span data-ttu-id="68e19-101">.NET Core 3,0 segue le procedure consigliate Unicode per la sostituzione di sequenze di byte UTF-8 in formato non corretto</span><span class="sxs-lookup"><span data-stu-id="68e19-101">.NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>

<span data-ttu-id="68e19-102">Quando la classe <xref:System.Text.UTF8Encoding> rileva una sequenza di byte UTF-8 in formato non corretto durante un'operazione di transcodifica da byte a carattere, la sequenza verrà sostituita con il carattere di sostituzione "" (U + FFFD) nella stringa di output.</span><span class="sxs-lookup"><span data-stu-id="68e19-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it will replace that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="68e19-103">.NET Core 3,0 differisce dalle versioni precedenti di .NET Core e dal .NET Framework seguendo la procedura consigliata Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.</span><span class="sxs-lookup"><span data-stu-id="68e19-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="68e19-104">Questa operazione fa parte di un impegno maggiore per migliorare la gestione UTF-8 in .NET, inclusi i nuovi <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> e i tipi di <xref:System.Text.Rune?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68e19-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="68e19-105">Al tipo <xref:System.Text.UTF8Encoding> è stato fornito un meccanismo di gestione degli errori migliorato in modo da produrre output coerente con i nuovi tipi introdotti.</span><span class="sxs-lookup"><span data-stu-id="68e19-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="68e19-106">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="68e19-106">Change description</span></span>

<span data-ttu-id="68e19-107">A partire da .NET Core 3,0, quando si transcodificano i byte in caratteri, la classe <xref:System.Text.UTF8Encoding> esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode.</span><span class="sxs-lookup"><span data-stu-id="68e19-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="68e19-108">Il meccanismo di sostituzione usato viene descritto dallo [standard Unicode, versione 12,0, sec. 3,9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione intitolata _U + FFFD Substitution of Maximum Subparts_.</span><span class="sxs-lookup"><span data-stu-id="68e19-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="68e19-109">Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="68e19-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="68e19-110">Inoltre, se l'istanza di <xref:System.Text.UTF8Encoding> è stata costruita con `throwOnInvalidBytes: true` (vedere la [documentazione del costruttore UTF8Encoding] (<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, l'istanza di `UTF8Encoding` continuerà a generare un input non valido anziché eseguire la sostituzione di U + FFFD.</span><span class="sxs-lookup"><span data-stu-id="68e19-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true` (see the [UTF8Encoding constructor documentation](<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span>

<span data-ttu-id="68e19-111">Nell'esempio seguente viene illustrato l'effetto di questa modifica con un input di 3 byte non valido:</span><span class="sxs-lookup"><span data-stu-id="68e19-111">The following illustrates the impact of this change with an invalid 3-byte input:</span></span>

|<span data-ttu-id="68e19-112">Input a 3 byte in formato non valido</span><span class="sxs-lookup"><span data-stu-id="68e19-112">Ill-formed 3-byte input</span></span>|<span data-ttu-id="68e19-113">Output prima di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="68e19-113">Output before .NET Core 3.0</span></span>|<span data-ttu-id="68e19-114">Output a partire da .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="68e19-114">Output starting with .NET Core 3.0</span></span>|
|---|---|---|
| `[ ED A0 90 ]` | <span data-ttu-id="68e19-115">`[ FFFD FFFD ]` (output a 2 caratteri)</span><span class="sxs-lookup"><span data-stu-id="68e19-115">`[ FFFD FFFD ]` (2-character output)</span></span>| <span data-ttu-id="68e19-116">`[ FFFD FFFD FFFD ]` (output di 3 caratteri)</span><span class="sxs-lookup"><span data-stu-id="68e19-116">`[ FFFD FFFD FFFD ]` (3-character output)</span></span>|

<span data-ttu-id="68e19-117">Questo output di 3 caratteri è l'output preferito, in base alla _tabella 3-9_ del file PDF standard Unicode collegato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="68e19-117">This 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="68e19-118">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="68e19-118">Version introduced</span></span>

<span data-ttu-id="68e19-119">3.0</span><span class="sxs-lookup"><span data-stu-id="68e19-119">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="68e19-120">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="68e19-120">Recommended action</span></span>

<span data-ttu-id="68e19-121">Non è richiesta alcuna azione da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="68e19-121">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="68e19-122">Category</span><span class="sxs-lookup"><span data-stu-id="68e19-122">Category</span></span>

<span data-ttu-id="68e19-123">CoreFx</span><span class="sxs-lookup"><span data-stu-id="68e19-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="68e19-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="68e19-124">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
