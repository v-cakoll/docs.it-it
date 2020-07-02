---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615662"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="d5a1f-101">Possibili errori in Windows 2003 per le app pubblicate con ClickOnce che usano un certificato per la firma del codice SHA-256</span><span class="sxs-lookup"><span data-stu-id="d5a1f-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="d5a1f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d5a1f-102">Details</span></span>

<span data-ttu-id="d5a1f-103">Il file eseguibile è firmato con SHA256.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="d5a1f-104">In precedenza, veniva firmato con SHA1 indipendentemente dal fatto che il certificato di firma del codice fosse SHA-1 o SHA-256.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="d5a1f-105">Si applica a:</span><span class="sxs-lookup"><span data-stu-id="d5a1f-105">This applies to:</span></span>

- <span data-ttu-id="d5a1f-106">Tutte le applicazioni compilate con Visual Studio 2012 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="d5a1f-107">Applicazioni compilate con Visual Studio 2010 o versioni precedenti su sistemi in cui è presente .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="d5a1f-108">Se inoltre è presente .NET Framework 4.5 o versione successiva, il manifesto ClickOnce viene firmato anche con SHA-256 per i certificati SHA-256 indipendentemente dalla versione di .NET Framework per cui è stato compilato.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d5a1f-109">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d5a1f-109">Suggestion</span></span>

<span data-ttu-id="d5a1f-110">La modifica della firma del file eseguibile di ClickOnce interessa solo i sistemi Windows Server 2003 in cui è richiesta l'installazione di quanto indicato nell'articolo 938397 della Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="d5a1f-111">La modifica relativa alla firma del manifesto con SHA-256 anche quando un'app è destinata a .NET Framework 4.0 o a versioni precedenti introduce una dipendenza del runtime da .NET Framework 4.5 o da una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d5a1f-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="d5a1f-112">Nome</span><span class="sxs-lookup"><span data-stu-id="d5a1f-112">Name</span></span>    | <span data-ttu-id="d5a1f-113">Valore</span><span class="sxs-lookup"><span data-stu-id="d5a1f-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d5a1f-114">Scope</span><span class="sxs-lookup"><span data-stu-id="d5a1f-114">Scope</span></span>   | <span data-ttu-id="d5a1f-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d5a1f-115">Edge</span></span>        |
| <span data-ttu-id="d5a1f-116">Version</span><span class="sxs-lookup"><span data-stu-id="d5a1f-116">Version</span></span> | <span data-ttu-id="d5a1f-117">4.5</span><span class="sxs-lookup"><span data-stu-id="d5a1f-117">4.5</span></span>         |
| <span data-ttu-id="d5a1f-118">Type</span><span class="sxs-lookup"><span data-stu-id="d5a1f-118">Type</span></span>    | <span data-ttu-id="d5a1f-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d5a1f-119">Retargeting</span></span> |
