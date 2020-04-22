---
ms.openlocfilehash: 820825f0545aa78729414c388385b339225b1235
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021620"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="3b206-101">Le istanze di EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivoCustom EncoderFallbackBuffer instances cannot fallback recursively</span><span class="sxs-lookup"><span data-stu-id="3b206-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="3b206-102">Le <xref:System.Text.EncoderFallbackBuffer> istanze personalizzate non possono eseguire il rollback in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="3b206-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="3b206-103">L'implementazione di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deve generare una sequenza di caratteri convertibile nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b206-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="3b206-104">In caso contrario, si verifica un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3b206-104">Otherwise, an exception occurs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3b206-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="3b206-105">Change description</span></span>

<span data-ttu-id="3b206-106">Durante un'operazione di transcodifica da carattere a byte, il runtime rileva sequenze UTF-16 in <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> formato non corretto o non convertibili e fornisce tali caratteri al metodo.</span><span class="sxs-lookup"><span data-stu-id="3b206-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3b206-107">Il `Fallback` metodo determina quali caratteri devono essere sostituiti con i dati non convertibili originali e questi caratteri vengono scaricati chiamando <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="3b206-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="3b206-108">Il runtime tenta quindi di transcodificare questi caratteri di sostituzione nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b206-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="3b206-109">Se l'operazione ha esito positivo, il runtime continua la transcodifica dal punto in cui è stata interrotta nella stringa di input originale.</span><span class="sxs-lookup"><span data-stu-id="3b206-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="3b206-110">In .NET Core Preview 7 e versioni <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> precedenti, le implementazioni personalizzate di possono restituire sequenze di caratteri non convertibili nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b206-110">In .NET Core Preview 7 and earlier versions, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="3b206-111">Se i caratteri sostituiti non possono essere transcodificati nella <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> codifica di destinazione, il <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> runtime richiama nuovamente il metodo con i caratteri di sostituzione, prevedendo che il metodo restituisca una nuova sequenza di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="3b206-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="3b206-112">Questo processo continua fino a quando il runtime vede una sostituzione convertibile ben formata o fino a quando non viene raggiunto un conteggio di ricorsione massimo.</span><span class="sxs-lookup"><span data-stu-id="3b206-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="3b206-113">A partire da .NET Core 3.0, le implementazioni personalizzate di devono restituire sequenze di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> caratteri convertibili nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b206-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="3b206-114">Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, viene generata un'eccezione. <xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="3b206-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="3b206-115">Il runtime non effettuerà più chiamate <xref:System.Text.EncoderFallbackBuffer> ricorsive nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="3b206-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="3b206-116">Questo comportamento si applica solo quando vengono soddisfatte tutte e tre le condizioni seguenti:This behavior only applies when all three of the following conditions are met:</span><span class="sxs-lookup"><span data-stu-id="3b206-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="3b206-117">Il runtime rileva una sequenza UTF-16 in formato non corretto o una sequenza UTF-16 che non può essere convertita nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b206-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="3b206-118">È <xref:System.Text.EncoderFallback> stata specificata una proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3b206-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="3b206-119">L'elemento personalizzato <xref:System.Text.EncoderFallback> tenta di sostituire una nuova sequenza UTF-16 non formata correttamente o non convertibile.</span><span class="sxs-lookup"><span data-stu-id="3b206-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3b206-120">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="3b206-120">Version introduced</span></span>

<span data-ttu-id="3b206-121">3.0</span><span class="sxs-lookup"><span data-stu-id="3b206-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3b206-122">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="3b206-122">Recommended action</span></span>

<span data-ttu-id="3b206-123">La maggior parte degli sviluppatori non deve intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="3b206-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="3b206-124">Se un'applicazione <xref:System.Text.EncoderFallback> utilizza <xref:System.Text.EncoderFallbackBuffer> una classe e <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> personalizzata, verificare che l'implementazione di popola il buffer di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> fallback con dati UTF-16 ben formati che sono direttamente convertibili nella codifica di destinazione quando il metodo viene richiamato per la prima volta dal runtime.</span><span class="sxs-lookup"><span data-stu-id="3b206-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="3b206-125">Category</span><span class="sxs-lookup"><span data-stu-id="3b206-125">Category</span></span>

<span data-ttu-id="3b206-126">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="3b206-126">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b206-127">API interessate</span><span class="sxs-lookup"><span data-stu-id="3b206-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
