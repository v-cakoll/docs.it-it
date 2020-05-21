---
ms.openlocfilehash: 00c32c10f77995284264e795d386f699082dcb84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721364"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a><span data-ttu-id="3e5cd-101">Le istanze EncoderFallbackBuffer personalizzate non possono eseguire il fallback in modo ricorsivo</span><span class="sxs-lookup"><span data-stu-id="3e5cd-101">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>

<span data-ttu-id="3e5cd-102">Le <xref:System.Text.EncoderFallbackBuffer> istanze personalizzate non possono eseguire il fallback in modo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-102">Custom <xref:System.Text.EncoderFallbackBuffer> instances cannot fall back recursively.</span></span> <span data-ttu-id="3e5cd-103">L'implementazione di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deve produrre una sequenza di caratteri convertibile nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-103">The implementation of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must result in a character sequence that is convertible to the destination encoding.</span></span> <span data-ttu-id="3e5cd-104">In caso contrario, si verificherà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-104">Otherwise, an exception occurs.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3e5cd-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="3e5cd-105">Change description</span></span>

<span data-ttu-id="3e5cd-106">Durante un'operazione di transcodifica da carattere a byte, il runtime rileva le sequenze UTF-16 non conformi o non convertibili e fornisce tali caratteri al <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-106">During a character-to-byte transcoding operation, the runtime detects ill-formed or nonconvertible UTF-16 sequences and provides those characters to the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3e5cd-107">Il `Fallback` metodo determina i caratteri che devono essere sostituiti dai dati non convertibili originali e questi caratteri vengono svuotati chiamando <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-107">The `Fallback` method determines which characters should be substituted for the original nonconvertible data, and these characters are drained by calling <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> in a loop.</span></span>

<span data-ttu-id="3e5cd-108">Il runtime tenta quindi di transcodificare questi caratteri di sostituzione nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-108">The runtime then attempts to transcode these substitution characters to the target encoding.</span></span> <span data-ttu-id="3e5cd-109">Se l'operazione ha esito positivo, il runtime continua la transcodifica dal punto in cui è stato interrotto nella stringa di input originale.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-109">If this operation succeeds, the runtime continues transcoding from where it left off in the original input string.</span></span>

<span data-ttu-id="3e5cd-110">In .NET Core Preview 7 e versioni precedenti, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> possono restituire sequenze di caratteri che non sono convertibili nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-110">In .NET Core Preview 7 and earlier versions, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> can return character sequences that are not convertible to the destination encoding.</span></span> <span data-ttu-id="3e5cd-111">Se i caratteri sostituiti non possono essere transcodificati nella codifica di destinazione, il runtime richiama di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> nuovo il metodo con i caratteri di sostituzione, aspettando <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> che il metodo restituisca una nuova sequenza di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-111">If the substituted characters cannot be transcoded to the target encoding, the runtime invokes the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> method once again with the substitution characters, expecting the <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> method to return a new substitution sequence.</span></span> <span data-ttu-id="3e5cd-112">Questo processo continua fino a quando il runtime non rileva una sostituzione corretta, convertibile o fino a quando non viene raggiunto il numero massimo di ricorsioni.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-112">This process continues until the runtime eventually sees a well-formed, convertible substitution, or until a maximum recursion count is reached.</span></span>

<span data-ttu-id="3e5cd-113">A partire da .NET Core 3,0, le implementazioni personalizzate di <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> devono restituire sequenze di caratteri convertibili nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-113">Starting with .NET Core 3.0, custom implementations of <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> must return character sequences that are convertible to the destination encoding.</span></span> <span data-ttu-id="3e5cd-114">Se i caratteri sostituiti non possono essere trascodificati nella codifica di destinazione, <xref:System.ArgumentException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-114">If the substituted characters cannot be transcoded to the target encoding, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="3e5cd-115">Il runtime non effettuerà più chiamate ricorsive nell' <xref:System.Text.EncoderFallbackBuffer> istanza.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-115">The runtime will no longer make recursive calls into the <xref:System.Text.EncoderFallbackBuffer> instance.</span></span>

<span data-ttu-id="3e5cd-116">Questo comportamento si applica solo quando vengono soddisfatte tutte e tre le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e5cd-116">This behavior only applies when all three of the following conditions are met:</span></span>

- <span data-ttu-id="3e5cd-117">Il runtime rileva una sequenza UTF-16 non corretta o una sequenza UTF-16 che non può essere convertita nella codifica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-117">The runtime detects an ill-formed UTF-16 sequence or a UTF-16 sequence that cannot be converted to the target encoding.</span></span>
- <span data-ttu-id="3e5cd-118"><xref:System.Text.EncoderFallback>È stato specificato un oggetto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-118">A custom <xref:System.Text.EncoderFallback> has been specified.</span></span>
- <span data-ttu-id="3e5cd-119">L'oggetto personalizzato <xref:System.Text.EncoderFallback> tenta di sostituire una nuova sequenza UTF-16 non in formato non corretto o non convertibile.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-119">The custom <xref:System.Text.EncoderFallback> attempts to substitute a new ill-formed or nonconvertible UTF-16 sequence.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3e5cd-120">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="3e5cd-120">Version introduced</span></span>

<span data-ttu-id="3e5cd-121">3.0</span><span class="sxs-lookup"><span data-stu-id="3e5cd-121">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3e5cd-122">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="3e5cd-122">Recommended action</span></span>

<span data-ttu-id="3e5cd-123">La maggior parte degli sviluppatori non deve intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-123">Most developers needn't take any action.</span></span>

<span data-ttu-id="3e5cd-124">Se un'applicazione usa una <xref:System.Text.EncoderFallback> classe e personalizzata <xref:System.Text.EncoderFallbackBuffer> , assicurarsi che l'implementazione di <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> compilerà il buffer di fallback con dati UTF-16 ben formati convertibili direttamente nella codifica di destinazione quando il <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> metodo viene richiamato per la prima volta dal runtime.</span><span class="sxs-lookup"><span data-stu-id="3e5cd-124">If an application uses a custom <xref:System.Text.EncoderFallback> and <xref:System.Text.EncoderFallbackBuffer> class, ensure the implementation of <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> populates the fallback buffer with well-formed UTF-16 data that is directly convertible to the target encoding when the <xref:System.Text.EncoderFallbackBuffer.Fallback%2A> method is first invoked by the runtime.</span></span>

#### <a name="category"></a><span data-ttu-id="3e5cd-125">Category</span><span class="sxs-lookup"><span data-stu-id="3e5cd-125">Category</span></span>

<span data-ttu-id="3e5cd-126">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="3e5cd-126">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3e5cd-127">API interessate</span><span class="sxs-lookup"><span data-stu-id="3e5cd-127">Affected APIs</span></span>

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
