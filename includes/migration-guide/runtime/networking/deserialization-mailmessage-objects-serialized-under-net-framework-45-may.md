---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620344"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="2b156-101">La deserializzazione di oggetti MailMessage serializzati in .NET Framework 4.5 può non riuscire</span><span class="sxs-lookup"><span data-stu-id="2b156-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="2b156-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2b156-102">Details</span></span>

<span data-ttu-id="2b156-103">A partire da .NET Framework 4.5, gli oggetti <xref:System.Web.Mail.MailMessage> possono includere caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="2b156-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="2b156-104">In .NET Framework 4, sono supportati solo caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="2b156-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="2b156-105">Gli oggetti <xref:System.Web.Mail.MailMessage> che contengono caratteri non ASCII e che vengono serializzati in .NET Framework 4.5 o versione successiva non possono essere deserializzati in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2b156-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2b156-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="2b156-106">Suggestion</span></span>

<span data-ttu-id="2b156-107">Quando si deserializza un oggetto <xref:System.Web.Mail.MailMessage>, verificare che il codice consenta la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="2b156-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="2b156-108">Nome</span><span class="sxs-lookup"><span data-stu-id="2b156-108">Name</span></span>    | <span data-ttu-id="2b156-109">Valore</span><span class="sxs-lookup"><span data-stu-id="2b156-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2b156-110">Scope</span><span class="sxs-lookup"><span data-stu-id="2b156-110">Scope</span></span>   |<span data-ttu-id="2b156-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="2b156-111">Minor</span></span>|
|<span data-ttu-id="2b156-112">Version</span><span class="sxs-lookup"><span data-stu-id="2b156-112">Version</span></span>|<span data-ttu-id="2b156-113">4.5</span><span class="sxs-lookup"><span data-stu-id="2b156-113">4.5</span></span>|
|<span data-ttu-id="2b156-114">Type</span><span class="sxs-lookup"><span data-stu-id="2b156-114">Type</span></span>|<span data-ttu-id="2b156-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="2b156-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2b156-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="2b156-116">Affected APIs</span></span>

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
