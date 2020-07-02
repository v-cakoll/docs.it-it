---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614425"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="d9123-101">Consentire i caratteri di controllo bidirezionali Unicode negli URI</span><span class="sxs-lookup"><span data-stu-id="d9123-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="d9123-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d9123-102">Details</span></span>

<span data-ttu-id="d9123-103">La specifica Unicode include vari caratteri di controllo speciali, usati per indicare l'orientamento del testo.</span><span class="sxs-lookup"><span data-stu-id="d9123-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="d9123-104">Nelle versioni precedenti di .NET Framework tali caratteri venivano erroneamente rimossi da tutti gli URI, anche se erano presenti con il formato di codifica con percentuali appropriato.</span><span class="sxs-lookup"><span data-stu-id="d9123-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="d9123-105">Per una maggior conformità con [RFC 3987](https://tools.ietf.org/html/rfc3987), ora tali caratteri sono consentiti negli URI.</span><span class="sxs-lookup"><span data-stu-id="d9123-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="d9123-106">Se vengono rilevati come non codificati in un URI, i caratteri vengono codificati con simboli di percentuale.</span><span class="sxs-lookup"><span data-stu-id="d9123-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="d9123-107">Se sono già codificati con simboli di percentuale, vengono lasciati invariati.</span><span class="sxs-lookup"><span data-stu-id="d9123-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d9123-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d9123-108">Suggestion</span></span>

<span data-ttu-id="d9123-109">Per le applicazioni destinate alle versioni di .NET Framework a partire da 4.7.2 il supporto dei caratteri Unicode bidirezionali è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9123-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="d9123-110">Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="d9123-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="d9123-111">Per le applicazioni che sono destinate a versioni precedenti di .NET Framework ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il supporto per i caratteri Unicode bidirezionali è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9123-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="d9123-112">È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="d9123-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="d9123-113">Nome</span><span class="sxs-lookup"><span data-stu-id="d9123-113">Name</span></span>    | <span data-ttu-id="d9123-114">Valore</span><span class="sxs-lookup"><span data-stu-id="d9123-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d9123-115">Scope</span><span class="sxs-lookup"><span data-stu-id="d9123-115">Scope</span></span>   | <span data-ttu-id="d9123-116">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d9123-116">Minor</span></span>       |
| <span data-ttu-id="d9123-117">Version</span><span class="sxs-lookup"><span data-stu-id="d9123-117">Version</span></span> | <span data-ttu-id="d9123-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d9123-118">4.7.2</span></span>       |
| <span data-ttu-id="d9123-119">Type</span><span class="sxs-lookup"><span data-stu-id="d9123-119">Type</span></span>    | <span data-ttu-id="d9123-120">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d9123-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d9123-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="d9123-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
