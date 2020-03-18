---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451888"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="4c5e2-101">Valore predefinito di HttpRequestMessage.Version modificato in 1.1</span><span class="sxs-lookup"><span data-stu-id="4c5e2-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="4c5e2-102">Il valore predefinito <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> della proprietà è stato modificato da 2.0 a 1.1.</span><span class="sxs-lookup"><span data-stu-id="4c5e2-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4c5e2-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4c5e2-103">Version introduced</span></span>

<span data-ttu-id="4c5e2-104">3.0</span><span class="sxs-lookup"><span data-stu-id="4c5e2-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="4c5e2-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="4c5e2-105">Change description</span></span>

<span data-ttu-id="4c5e2-106">In .NET Core da 1.0 a 2.0, il valore predefinito della <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> proprietà è 1.1.</span><span class="sxs-lookup"><span data-stu-id="4c5e2-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="4c5e2-107">A partire da .NET Core 2.1, è stato modificato in 2.1.Starting with .NET Core 2.1, it was changed to 2.1.</span><span class="sxs-lookup"><span data-stu-id="4c5e2-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="4c5e2-108">A partire da .NET Core 3.0, il <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> numero di versione predefinito restituito dalla proprietà è ancora una volta 1.1.Starting with .NET Core 3.0, the default version number returned by the property is once 1.1.</span><span class="sxs-lookup"><span data-stu-id="4c5e2-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4c5e2-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="4c5e2-109">Recommended action</span></span>

<span data-ttu-id="4c5e2-110">Aggiornare il codice se <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> dipende dalla proprietà che restituisce un valore predefinito di 2.0.Update your code if it depends on the property returning a default value of 2.0.</span><span class="sxs-lookup"><span data-stu-id="4c5e2-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="4c5e2-111">Category</span><span class="sxs-lookup"><span data-stu-id="4c5e2-111">Category</span></span>

<span data-ttu-id="4c5e2-112">Rete</span><span class="sxs-lookup"><span data-stu-id="4c5e2-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4c5e2-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="4c5e2-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
