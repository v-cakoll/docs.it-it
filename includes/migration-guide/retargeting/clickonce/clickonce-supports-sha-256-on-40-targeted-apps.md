---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615654"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="ffdf6-101">ClickOnce supporta SHA-256 per le app destinate alla versione 4.0</span><span class="sxs-lookup"><span data-stu-id="ffdf6-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="ffdf6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ffdf6-102">Details</span></span>

<span data-ttu-id="ffdf6-103">In precedenza, un'app ClickOnce con certificato firmato con SHA-256 avrebbe richiesto la presenza di .NET Framework 4.5 o versioni successive, anche se l'app era destinata alla versione 4.0.</span><span class="sxs-lookup"><span data-stu-id="ffdf6-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="ffdf6-104">È ora possibile eseguire le app ClickOnce destinate a .NET Framework 4.0 in .NET Framework 4.0, anche se firmate con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="ffdf6-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ffdf6-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ffdf6-105">Suggestion</span></span>

<span data-ttu-id="ffdf6-106">Questa modifica rimuove tale dipendenza e consente di usare i certificati SHA-256 per firmare le app ClickOnce destinate a .NET Framework 4 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ffdf6-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="ffdf6-107">Nome</span><span class="sxs-lookup"><span data-stu-id="ffdf6-107">Name</span></span>    | <span data-ttu-id="ffdf6-108">Valore</span><span class="sxs-lookup"><span data-stu-id="ffdf6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ffdf6-109">Scope</span><span class="sxs-lookup"><span data-stu-id="ffdf6-109">Scope</span></span>   | <span data-ttu-id="ffdf6-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="ffdf6-110">Minor</span></span>       |
| <span data-ttu-id="ffdf6-111">Version</span><span class="sxs-lookup"><span data-stu-id="ffdf6-111">Version</span></span> | <span data-ttu-id="ffdf6-112">4.6</span><span class="sxs-lookup"><span data-stu-id="ffdf6-112">4.6</span></span>         |
| <span data-ttu-id="ffdf6-113">Type</span><span class="sxs-lookup"><span data-stu-id="ffdf6-113">Type</span></span>    | <span data-ttu-id="ffdf6-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="ffdf6-114">Retargeting</span></span> |
