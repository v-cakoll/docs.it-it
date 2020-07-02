---
ms.openlocfilehash: 57f68c10d5d1edc9b8deaca2f4fe7edda2dd69b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620394"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="c5d51-101">L'oggetto System.ServiceModel.Web.WebServiceHost non aggiunge più un endpoint predefinito</span><span class="sxs-lookup"><span data-stu-id="c5d51-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="c5d51-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c5d51-102">Details</span></span>

<span data-ttu-id="c5d51-103">L'oggetto <xref:System.ServiceModel.Web.WebServiceHost> non aggiunge più un endpoint predefinito se è stato aggiunto un endpoint esplicito tramite il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5d51-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c5d51-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c5d51-104">Suggestion</span></span>

<span data-ttu-id="c5d51-105">Se gli utenti si aspettano di essere in grado di connettersi a un endpoint predefinito e altri endpoint espliciti sono state aggiunti a <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, deve essere possibile anche aggiungere endpoint predefiniti in modo esplicito mediante <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c5d51-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="c5d51-106">Nome</span><span class="sxs-lookup"><span data-stu-id="c5d51-106">Name</span></span>    | <span data-ttu-id="c5d51-107">Valore</span><span class="sxs-lookup"><span data-stu-id="c5d51-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c5d51-108">Scope</span><span class="sxs-lookup"><span data-stu-id="c5d51-108">Scope</span></span>   |<span data-ttu-id="c5d51-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="c5d51-109">Minor</span></span>|
|<span data-ttu-id="c5d51-110">Version</span><span class="sxs-lookup"><span data-stu-id="c5d51-110">Version</span></span>|<span data-ttu-id="c5d51-111">4.5</span><span class="sxs-lookup"><span data-stu-id="c5d51-111">4.5</span></span>|
|<span data-ttu-id="c5d51-112">Type</span><span class="sxs-lookup"><span data-stu-id="c5d51-112">Type</span></span>|<span data-ttu-id="c5d51-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="c5d51-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c5d51-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="c5d51-114">Affected APIs</span></span>

-<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li></ul>|
