---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235754"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="3d0fc-101">La deserializzazione di oggetti MailMessage serializzati in .NET Framework 4.5 può non riuscire</span><span class="sxs-lookup"><span data-stu-id="3d0fc-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3d0fc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3d0fc-102">Details</span></span>|<span data-ttu-id="3d0fc-103">A partire da .NET Framework 4.5, gli oggetti <xref:System.Web.Mail.MailMessage> possono includere caratteri non ASCII.</span><span class="sxs-lookup"><span data-stu-id="3d0fc-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="3d0fc-104">In .NET Framework 4, sono supportati solo caratteri ASCII.</span><span class="sxs-lookup"><span data-stu-id="3d0fc-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <xref:System.Web.Mail.MailMessage> <span data-ttu-id="3d0fc-105">Gli oggetti MailMessage che contengono caratteri non ASCII e che vengono serializzati in .NET Framework 4.5 o versione successiva non possono essere deserializzati in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3d0fc-105">objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="3d0fc-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3d0fc-106">Suggestion</span></span>|<span data-ttu-id="3d0fc-107">Quando si deserializza un oggetto <xref:System.Web.Mail.MailMessage>, verificare che il codice consenta la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3d0fc-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="3d0fc-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="3d0fc-108">Scope</span></span>|<span data-ttu-id="3d0fc-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="3d0fc-109">Minor</span></span>|
|<span data-ttu-id="3d0fc-110">Versione</span><span class="sxs-lookup"><span data-stu-id="3d0fc-110">Version</span></span>|<span data-ttu-id="3d0fc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="3d0fc-111">4.5</span></span>|
|<span data-ttu-id="3d0fc-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d0fc-112">Type</span></span>|<span data-ttu-id="3d0fc-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="3d0fc-113">Runtime</span></span>|
|<span data-ttu-id="3d0fc-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="3d0fc-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
