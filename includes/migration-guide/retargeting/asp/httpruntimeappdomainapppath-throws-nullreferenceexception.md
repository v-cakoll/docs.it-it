---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617535"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="b2285-101">HttpRuntime.AppDomainAppPath genera un'eccezione NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="b2285-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="b2285-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b2285-102">Details</span></span>

<span data-ttu-id="b2285-103">In .NET Framework 4.6.2, il runtime genera una `T:System.NullReferenceException` durante il recupero di un valore `P:System.Web.HttpRuntime.AppDomainAppPath` che include caratteri Null. In .NET Framework 4.6.1 e versioni precedenti, il runtime genera una `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="b2285-103">In the .NET Framework 4.6.2, the runtime throws a `T:System.NullReferenceException` when retrieving a `P:System.Web.HttpRuntime.AppDomainAppPath` value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an `T:System.ArgumentNullException`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b2285-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b2285-104">Suggestion</span></span>

<span data-ttu-id="b2285-105">È possibile eseguire una delle operazioni seguenti per rispondere a questa modifica:</span><span class="sxs-lookup"><span data-stu-id="b2285-105">You can do either of the follow to respond to this change:</span></span>

- <span data-ttu-id="b2285-106">Se l'applicazione è in esecuzione in .NET Framework 4.6.2, gestire `T:System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="b2285-106">Handle the `T:System.NullReferenceException` if you application is running on the .NET Framework 4.6.2.</span></span>
- <span data-ttu-id="b2285-107">Eseguire l'aggiornamento a .NET Framework 4.7, che consente di ripristinare il comportamento precedente e genera un'eccezione `T:System.ArgumentNullException`.</span><span class="sxs-lookup"><span data-stu-id="b2285-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an `T:System.ArgumentNullException`.</span></span>

| <span data-ttu-id="b2285-108">Nome</span><span class="sxs-lookup"><span data-stu-id="b2285-108">Name</span></span>    | <span data-ttu-id="b2285-109">Valore</span><span class="sxs-lookup"><span data-stu-id="b2285-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b2285-110">Scope</span><span class="sxs-lookup"><span data-stu-id="b2285-110">Scope</span></span>   | <span data-ttu-id="b2285-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b2285-111">Edge</span></span>        |
| <span data-ttu-id="b2285-112">Version</span><span class="sxs-lookup"><span data-stu-id="b2285-112">Version</span></span> | <span data-ttu-id="b2285-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b2285-113">4.6.2</span></span>       |
| <span data-ttu-id="b2285-114">Type</span><span class="sxs-lookup"><span data-stu-id="b2285-114">Type</span></span>    | <span data-ttu-id="b2285-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="b2285-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b2285-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="b2285-116">Affected APIs</span></span>

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>
