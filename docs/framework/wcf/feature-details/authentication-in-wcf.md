---
title: Autenticazione in WCF
description: Informazioni sui diversi meccanismi in WCF che forniscono l'autenticazione, ad esempio l'autenticazione di Windows, i certificati X. 509 e il nome utente e la password.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 4c3348cfb84b8571dc1f24b774ffcd691aaa5001
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247520"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="4768c-103">Autenticazione in WCF</span><span class="sxs-lookup"><span data-stu-id="4768c-103">Authentication in WCF</span></span>
<span data-ttu-id="4768c-104">Negli argomenti seguenti vengono illustrati diversi meccanismi di Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio autenticazione di Windows, certificati X. 509 e nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="4768c-104">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4768c-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4768c-105">In This Section</span></span>  
 [<span data-ttu-id="4768c-106">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="4768c-106">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="4768c-107">Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4768c-107">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="4768c-108">In questo argomento viene illustrato il modo in cui i servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4768c-108">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="4768c-109">Procedura: usare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="4768c-109">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="4768c-110">Viene dimostrato come integrare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="4768c-110">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="4768c-111">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="4768c-111">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="4768c-112">Come ulteriore sicurezza, un client può autenticare il servizio specificando l' *identità* prevista del servizio.</span><span class="sxs-lookup"><span data-stu-id="4768c-112">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="4768c-113">Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4768c-113">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="4768c-114">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="4768c-114">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="4768c-115">Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="4768c-115">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="4768c-116">Debug degli errori di autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="4768c-116">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="4768c-117">Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4768c-117">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4768c-118">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="4768c-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="4768c-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4768c-119">Related Sections</span></span>  
 [<span data-ttu-id="4768c-120">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="4768c-120">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="4768c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4768c-121">See also</span></span>

- [<span data-ttu-id="4768c-122">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="4768c-122">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="4768c-123">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4768c-123">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
