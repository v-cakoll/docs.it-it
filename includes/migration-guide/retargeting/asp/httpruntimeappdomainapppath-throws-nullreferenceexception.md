---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859073"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="afd2e-101">HttpRuntime.AppDomainAppPath genera un'eccezione NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="afd2e-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="afd2e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="afd2e-102">Details</span></span>|<span data-ttu-id="afd2e-103">In .NET Framework 4.6.2, il runtime genera una <code>T:System.NullReferenceException</code> durante il recupero di un valore <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> che include caratteri Null. In .NET Framework 4.6.1 e versioni precedenti, il runtime genera una <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="afd2e-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="afd2e-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="afd2e-104">Suggestion</span></span>|<span data-ttu-id="afd2e-105">È possibile eseguire una delle operazioni seguenti per rispondere a questa modifica:</span><span class="sxs-lookup"><span data-stu-id="afd2e-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="afd2e-106">Se l'applicazione è in esecuzione in .NET Framework 4.6.2, gestire <code>T:System.NullReferenceException</code>.</span><span class="sxs-lookup"><span data-stu-id="afd2e-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="afd2e-107">Eseguire l'aggiornamento a .NET Framework 4.7, che consente di ripristinare il comportamento precedente e genera un'eccezione <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="afd2e-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="afd2e-108">Scope</span><span class="sxs-lookup"><span data-stu-id="afd2e-108">Scope</span></span>|<span data-ttu-id="afd2e-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="afd2e-109">Edge</span></span>|
|<span data-ttu-id="afd2e-110">Versione</span><span class="sxs-lookup"><span data-stu-id="afd2e-110">Version</span></span>|<span data-ttu-id="afd2e-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="afd2e-111">4.6.2</span></span>|
|<span data-ttu-id="afd2e-112">Type</span><span class="sxs-lookup"><span data-stu-id="afd2e-112">Type</span></span>|<span data-ttu-id="afd2e-113">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="afd2e-113">Retargeting</span></span>|
|<span data-ttu-id="afd2e-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="afd2e-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
