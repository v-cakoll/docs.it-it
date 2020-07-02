---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617206"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="7c2e1-101">L'analisi di System.Uri è conforme a RFC 3987</span><span class="sxs-lookup"><span data-stu-id="7c2e1-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="7c2e1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7c2e1-102">Details</span></span>

<span data-ttu-id="7c2e1-103">L'analisi URI ha subito vari cambiamenti in .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="7c2e1-104">Si noti, tuttavia, che queste modifiche influiscono solo sul codice destinato a .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="7c2e1-105">Se un file binario è destinato a .NET Framework 4.0, viene rispettato il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="7c2e1-106">Le modifiche introdotte per l'analisi URI in .NET Framework 4.5 includono:</span><span class="sxs-lookup"><span data-stu-id="7c2e1-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="7c2e1-107">L'analisi URI eseguirà la normalizzazione e il controllo dei caratteri in base alle regole URI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="7c2e1-108">Il formato C di normalizzazione Unicode verrà applicato solo alla parte host dell'URI.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="7c2e1-109">Gli URI mailto: non validi causeranno ora un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="7c2e1-110">I punti finali alla fine di un segmento di percorso vengono ora mantenuti.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="7c2e1-111">Negli URI `file://` non viene usato un codice di escape per il carattere `?`.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="7c2e1-112">I caratteri di controllo Unicode da `U+0080` a `U+009F` non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="7c2e1-113">Per i caratteri virgola `,` o `%2c` non viene rimosso automaticamente il codice di escape.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7c2e1-114">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7c2e1-114">Suggestion</span></span>

<span data-ttu-id="7c2e1-115">Se la semantica di analisi URI di .NET Framework 4.0 precedente è ancora necessaria, anche se spesso non lo è, è possibile usarla scegliendo .NET Framework 4.0 come destinazione.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="7c2e1-116">A tale scopo è possibile usare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> nell'assembly o l'interfaccia utente del sistema di progetti di Visual Studio nella pagina delle proprietà del progetto.</span><span class="sxs-lookup"><span data-stu-id="7c2e1-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="7c2e1-117">Nome</span><span class="sxs-lookup"><span data-stu-id="7c2e1-117">Name</span></span>    | <span data-ttu-id="7c2e1-118">Valore</span><span class="sxs-lookup"><span data-stu-id="7c2e1-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7c2e1-119">Scope</span><span class="sxs-lookup"><span data-stu-id="7c2e1-119">Scope</span></span>   | <span data-ttu-id="7c2e1-120">Principale</span><span class="sxs-lookup"><span data-stu-id="7c2e1-120">Major</span></span>       |
| <span data-ttu-id="7c2e1-121">Version</span><span class="sxs-lookup"><span data-stu-id="7c2e1-121">Version</span></span> | <span data-ttu-id="7c2e1-122">4.5</span><span class="sxs-lookup"><span data-stu-id="7c2e1-122">4.5</span></span>         |
| <span data-ttu-id="7c2e1-123">Type</span><span class="sxs-lookup"><span data-stu-id="7c2e1-123">Type</span></span>    | <span data-ttu-id="7c2e1-124">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7c2e1-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="7c2e1-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="7c2e1-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
