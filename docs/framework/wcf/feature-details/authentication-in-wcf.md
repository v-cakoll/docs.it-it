---
title: Autenticazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: b513c9713bd2c04e125915d1a0a87c86ce249666
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597644"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="c92a7-102">Autenticazione in WCF</span><span class="sxs-lookup"><span data-stu-id="c92a7-102">Authentication in WCF</span></span>
<span data-ttu-id="c92a7-103">Negli argomenti seguenti vengono illustrati diversi meccanismi di Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio autenticazione di Windows, certificati X. 509 e nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="c92a7-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c92a7-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c92a7-104">In This Section</span></span>  
 [<span data-ttu-id="c92a7-105">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c92a7-105">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="c92a7-106">Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="c92a7-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="c92a7-107">In questo argomento viene illustrato il modo in cui i servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c92a7-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="c92a7-108">Procedura: usare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="c92a7-108">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="c92a7-109">Viene dimostrato come integrare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="c92a7-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="c92a7-110">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c92a7-110">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="c92a7-111">Come ulteriore sicurezza, un client può autenticare il servizio specificando l' *identità* prevista del servizio.</span><span class="sxs-lookup"><span data-stu-id="c92a7-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="c92a7-112">Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c92a7-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="c92a7-113">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="c92a7-113">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="c92a7-114">Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="c92a7-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="c92a7-115">Debug degli errori di autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="c92a7-115">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="c92a7-116">Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c92a7-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c92a7-117">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="c92a7-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="c92a7-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c92a7-118">Related Sections</span></span>  
 [<span data-ttu-id="c92a7-119">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="c92a7-119">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="c92a7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c92a7-120">See also</span></span>

- [<span data-ttu-id="c92a7-121">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="c92a7-121">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="c92a7-122">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c92a7-122">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
