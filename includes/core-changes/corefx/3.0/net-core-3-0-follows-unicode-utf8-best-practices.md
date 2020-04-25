---
ms.openlocfilehash: becae23cd810623bbb33c693b707c2d4735aeece
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158475"
---
### <a name="replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines"></a><span data-ttu-id="96011-101">La sostituzione di sequenze di byte UTF-8 in formato non corretto segue le linee guida Unicode</span><span class="sxs-lookup"><span data-stu-id="96011-101">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>

<span data-ttu-id="96011-102">Quando la <xref:System.Text.UTF8Encoding> classe rileva una sequenza di byte UTF-8 non corretta durante un'operazione di transcodifica da byte a carattere, sostituisce quella sequenza con un carattere di sostituzione '' (U + FFFD) nella stringa di output.</span><span class="sxs-lookup"><span data-stu-id="96011-102">When the <xref:System.Text.UTF8Encoding> class encounters an ill-formed UTF-8 byte sequence during a byte-to-character transcoding operation, it replaces that sequence with a '�' (U+FFFD REPLACEMENT CHARACTER) character in the output string.</span></span> <span data-ttu-id="96011-103">.NET Core 3,0 differisce dalle versioni precedenti di .NET Core e dal .NET Framework seguendo la procedura consigliata Unicode per eseguire questa sostituzione durante l'operazione di transcodifica.</span><span class="sxs-lookup"><span data-stu-id="96011-103">.NET Core 3.0 differs from previous versions of .NET Core and the .NET Framework by following the Unicode best practice for performing this replacement during the transcoding operation.</span></span>

<span data-ttu-id="96011-104">Questa operazione fa parte di un impegno maggiore per migliorare la gestione UTF-8 in .NET, inclusi i <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> nuovi <xref:System.Text.Rune?displayProperty=nameWithType> tipi e.</span><span class="sxs-lookup"><span data-stu-id="96011-104">This is part of a larger effort to improve UTF-8 handling throughout .NET, including by the new <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> and <xref:System.Text.Rune?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="96011-105">Al <xref:System.Text.UTF8Encoding> tipo sono stati assegnati meccanismi di gestione degli errori migliorati in modo da produrre output coerente con i nuovi tipi introdotti.</span><span class="sxs-lookup"><span data-stu-id="96011-105">The <xref:System.Text.UTF8Encoding> type was given improved error handling mechanics so that it produces output consistent with the newly introduced types.</span></span>

#### <a name="change-description"></a><span data-ttu-id="96011-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="96011-106">Change description</span></span>

<span data-ttu-id="96011-107">A partire da .NET Core 3,0, quando si transcodificano i byte <xref:System.Text.UTF8Encoding> in caratteri, la classe esegue la sostituzione dei caratteri in base alle procedure consigliate Unicode.</span><span class="sxs-lookup"><span data-stu-id="96011-107">Starting with .NET Core 3.0, when transcoding bytes to characters, the <xref:System.Text.UTF8Encoding> class performs character substitution based on Unicode best practices.</span></span> <span data-ttu-id="96011-108">Il meccanismo di sostituzione usato viene descritto dallo [standard Unicode, versione 12,0, sec. 3,9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) nell'intestazione intitolata _U + FFFD Substitution of Maximum Subparts_.</span><span class="sxs-lookup"><span data-stu-id="96011-108">The substitution mechanism used is described by [The Unicode Standard, Version 12.0, Sec. 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) in the heading titled _U+FFFD Substitution of Maximal Subparts_.</span></span>

<span data-ttu-id="96011-109">Questo comportamento si applica _solo_ quando la sequenza di byte di input contiene dati UTF-8 in formato non corretto.</span><span class="sxs-lookup"><span data-stu-id="96011-109">This behavior _only_ applies when the input byte sequence contains ill-formed UTF-8 data.</span></span> <span data-ttu-id="96011-110">Inoltre, se l' <xref:System.Text.UTF8Encoding> istanza è stata costruita con `throwOnInvalidBytes: true`, l' `UTF8Encoding` istanza continuerà a generare un input non valido anziché eseguire la sostituzione di U + FFFD.</span><span class="sxs-lookup"><span data-stu-id="96011-110">Additionally, if the <xref:System.Text.UTF8Encoding> instance has been constructed with `throwOnInvalidBytes: true`, the `UTF8Encoding` instance will continue to throw on invalid input rather than perform U+FFFD replacement.</span></span> <span data-ttu-id="96011-111">Per ulteriori informazioni sul `UTF8Encoding` costruttore, vedere. <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)></span><span class="sxs-lookup"><span data-stu-id="96011-111">For more information about the `UTF8Encoding` constructor, see <xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>.</span></span>

<span data-ttu-id="96011-112">La tabella seguente illustra l'effetto di questa modifica con un input di 3 byte non valido:</span><span class="sxs-lookup"><span data-stu-id="96011-112">The following table illustrates the impact of this change with an invalid 3-byte input:</span></span>

| <span data-ttu-id="96011-113">Input a 3 byte in formato non valido</span><span class="sxs-lookup"><span data-stu-id="96011-113">Ill-formed 3-byte input</span></span> | <span data-ttu-id="96011-114">Output prima di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="96011-114">Output before .NET Core 3.0</span></span>          | <span data-ttu-id="96011-115">Output a partire da .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="96011-115">Output starting with .NET Core 3.0</span></span>        |
|-------------------------|--------------------------------------|-------------------------------------------|
| `[ ED A0 90 ]`          | <span data-ttu-id="96011-116">`[ FFFD FFFD ]`(output a 2 caratteri)</span><span class="sxs-lookup"><span data-stu-id="96011-116">`[ FFFD FFFD ]` (2-character output)</span></span> | <span data-ttu-id="96011-117">`[ FFFD FFFD FFFD ]`(output di 3 caratteri)</span><span class="sxs-lookup"><span data-stu-id="96011-117">`[ FFFD FFFD FFFD ]` (3-character output)</span></span> |

<span data-ttu-id="96011-118">L'output di 3 caratteri è l'output preferito, in base alla _tabella 3-9_ del file PDF standard Unicode collegato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="96011-118">The 3-char output is the preferred output, according to _Table 3-9_ of the previously linked Unicode Standard PDF.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="96011-119">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="96011-119">Version introduced</span></span>

<span data-ttu-id="96011-120">3.0</span><span class="sxs-lookup"><span data-stu-id="96011-120">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="96011-121">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="96011-121">Recommended action</span></span>

<span data-ttu-id="96011-122">Non è richiesta alcuna azione da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="96011-122">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="96011-123">Category</span><span class="sxs-lookup"><span data-stu-id="96011-123">Category</span></span>

<span data-ttu-id="96011-124">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="96011-124">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="96011-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="96011-125">Affected APIs</span></span>

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->
