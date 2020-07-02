---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614448"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="d5fc3-101">Verificare che System.Uri usi un set di caratteri riservati coerente</span><span class="sxs-lookup"><span data-stu-id="d5fc3-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="d5fc3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d5fc3-102">Details</span></span>

<span data-ttu-id="d5fc3-103">In <xref:System.Uri?displayProperty=fullName>, alcuni caratteri codificati con percentuali che in determinati casi apparivano come non codificati ora sono codificati in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="d5fc3-104">Questo si verifica in tutte le proprietà e i metodi che accedono ai componenti path, query, fragment o userinfo dell'URI.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="d5fc3-105">Il comportamento viene modificato solo quando entrambe le condizioni seguenti sono vere:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="d5fc3-106">L'URI contiene il formato codificato di uno qualsiasi dei caratteri riservati seguenti: `:`, `'`, `(`, `)`, `!` o `*`.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="d5fc3-107">L'URI contiene un carattere non riservato Unicode o codificato.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="d5fc3-108">Se entrambe le precedenti condizioni sono vere, i caratteri riservati codificati restano codificati.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="d5fc3-109">Nelle versioni di .NET Framework precedenti i caratteri vengono decodificati.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d5fc3-110">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d5fc3-110">Suggestion</span></span>

<span data-ttu-id="d5fc3-111">Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7.2, il nuovo comportamento di rimozione della codifica è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="d5fc3-112">Se questa modifica non è opportuna, è possibile disabilitarla aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla sezione `<runtime>` del file di configurazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="d5fc3-113">Per le applicazioni che sono destinate a versioni di .NET Framework precedenti ma vengono eseguite con versioni a partire da .NET Framework 4.7.2, il nuovo comportamento di rimozione della codifica è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d5fc3-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="d5fc3-114">È possibile abilitarlo aggiungendo l'opzione [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente alla `<runtime>` sezione del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="d5fc3-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="d5fc3-115">Nome</span><span class="sxs-lookup"><span data-stu-id="d5fc3-115">Name</span></span>    | <span data-ttu-id="d5fc3-116">Valore</span><span class="sxs-lookup"><span data-stu-id="d5fc3-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d5fc3-117">Scope</span><span class="sxs-lookup"><span data-stu-id="d5fc3-117">Scope</span></span>   | <span data-ttu-id="d5fc3-118">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d5fc3-118">Minor</span></span>       |
| <span data-ttu-id="d5fc3-119">Version</span><span class="sxs-lookup"><span data-stu-id="d5fc3-119">Version</span></span> | <span data-ttu-id="d5fc3-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="d5fc3-120">4.7.2</span></span>       |
| <span data-ttu-id="d5fc3-121">Type</span><span class="sxs-lookup"><span data-stu-id="d5fc3-121">Type</span></span>    | <span data-ttu-id="d5fc3-122">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d5fc3-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d5fc3-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="d5fc3-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
