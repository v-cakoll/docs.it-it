---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621292"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="9af86-101">Il valore AppDomainSetup.DynamicBase non è più generato in modo casuale da UseRandomizedStringHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="9af86-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

#### <a name="details"></a><span data-ttu-id="9af86-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9af86-102">Details</span></span>

<span data-ttu-id="9af86-103">Prima di .NET Framework 4.6, il valore di <xref:System.AppDomainSetup.DynamicBase> sarebbe stato casuale tra i domini applicazione o tra i processi con l'impostazione UseRandomizedStringHashAlgorithm abilitata nel file di configurazione dell'app.</span><span class="sxs-lookup"><span data-stu-id="9af86-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="9af86-104">A partire da .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> restituirà un risultato stabile tra istanze diverse di un'app in esecuzione e tra domini app diversi.</span><span class="sxs-lookup"><span data-stu-id="9af86-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="9af86-105">Le basi dinamiche saranno comunque diverse per app differenti. Questa modifica rimuove solo l'elemento di denominazione casuale per le diverse istanze della stessa app.</span><span class="sxs-lookup"><span data-stu-id="9af86-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9af86-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9af86-106">Suggestion</span></span>

<span data-ttu-id="9af86-107">Tenere presente che l'abilitazione di <code>UseRandomizedStringHashAlgorithm</code> non comporterà la generazione casuale di <xref:System.AppDomainSetup.DynamicBase>.</span><span class="sxs-lookup"><span data-stu-id="9af86-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="9af86-108">Se è necessaria una base casuale, devono essere prodotta nel codice dell'app invece che tramite questa API.</span><span class="sxs-lookup"><span data-stu-id="9af86-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>

| <span data-ttu-id="9af86-109">Nome</span><span class="sxs-lookup"><span data-stu-id="9af86-109">Name</span></span>    | <span data-ttu-id="9af86-110">Valore</span><span class="sxs-lookup"><span data-stu-id="9af86-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9af86-111">Scope</span><span class="sxs-lookup"><span data-stu-id="9af86-111">Scope</span></span>   |<span data-ttu-id="9af86-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9af86-112">Edge</span></span>|
|<span data-ttu-id="9af86-113">Version</span><span class="sxs-lookup"><span data-stu-id="9af86-113">Version</span></span>|<span data-ttu-id="9af86-114">4.6</span><span class="sxs-lookup"><span data-stu-id="9af86-114">4.6</span></span>|
|<span data-ttu-id="9af86-115">Type</span><span class="sxs-lookup"><span data-stu-id="9af86-115">Type</span></span>|<span data-ttu-id="9af86-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="9af86-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9af86-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="9af86-117">Affected APIs</span></span>

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
