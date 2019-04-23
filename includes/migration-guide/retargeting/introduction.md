---
ms.openlocfilehash: d4f22aa41eb7aeffd655d980cb8418649462273e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757756"
---
## <a name="introduction"></a><span data-ttu-id="3f9d3-101">Introduzione</span><span class="sxs-lookup"><span data-stu-id="3f9d3-101">Introduction</span></span>
<span data-ttu-id="3f9d3-102">Le modifiche di reindirizzamento influiscono sulle app che vengono ricompilate per una versione diversa di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-102">Retargeting changes affect apps that are recompiled to target a different .NET Framework.</span></span> <span data-ttu-id="3f9d3-103">e comprendono:</span><span class="sxs-lookup"><span data-stu-id="3f9d3-103">They include:</span></span>

* <span data-ttu-id="3f9d3-104">Modifiche all'ambiente in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-104">Changes in the design-time environment.</span></span> <span data-ttu-id="3f9d3-105">Gli strumenti di compilazione, ad esempio, possono generare avvisi mentre in precedenza non lo facevano.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-105">For example, build tools may emit warnings when previously they did not.</span></span>

* <span data-ttu-id="3f9d3-106">Modifiche all'ambiente di runtime.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-106">Changes in the runtime environment.</span></span> <span data-ttu-id="3f9d3-107">Queste influiscono solo sulle app destinate specificamente a una versione diversa di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-107">These affect only apps that specifically target the retargeted .NET Framework.</span></span> <span data-ttu-id="3f9d3-108">Le app destinate a versioni precedenti di .NET Framework si comportano come se venissero eseguite in tali versioni.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-108">Apps that target previous versions of the .NET Framework behave as they did when running under those versions.</span></span>

<span data-ttu-id="3f9d3-109">Negli argomenti che descrivono le modifiche di reindirizzamento i singoli elementi sono stati classificati in base all'impatto previsto, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="3f9d3-109">In the topics that describe retargeting changes, we have classified individual items by their expected impact, as follows:</span></span>

<span data-ttu-id="3f9d3-110">**Principale** Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-110">**Major** This is a significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="3f9d3-111">**Secondario** Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-111">**Minor** This is a change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="3f9d3-112">**Caso limite** Una modifica che influisce sulle app in scenari molto specifici e non comuni.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-112">**Edge case** This is a change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="3f9d3-113">**Trasparente** Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-113">**Transparent** This is a change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="3f9d3-114">L'app non dovrebbe richiedere variazioni a causa di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="3f9d3-114">The app should not require modification because of this change.</span></span>
