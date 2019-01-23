---
title: Autenticazione in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 22bfd7edf0ca0e9eb57e63c168c783f25782d607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523922"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="663ab-102">Autenticazione in WCF</span><span class="sxs-lookup"><span data-stu-id="663ab-102">Authentication in WCF</span></span>
<span data-ttu-id="663ab-103">Gli argomenti seguenti illustrano svariati meccanismi diversi in Windows Communication Foundation (WCF) che forniscono l'autenticazione, ad esempio, l'autenticazione di Windows, i certificati X.509 e nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="663ab-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="663ab-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="663ab-104">In This Section</span></span>  
 [<span data-ttu-id="663ab-105">Procedura: Usare il Provider di appartenenze ASP.NET</span><span class="sxs-lookup"><span data-stu-id="663ab-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="663ab-106">Le funzionalità ASP.NET comprendono un provider di appartenenze e ruoli, un database in cui archiviare coppie di nome utente e password per l'autenticazione e ruoli utente per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="663ab-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="663ab-107">Questo argomento viene illustrato come servizi WCF possono utilizzare lo stesso database per autenticare e autorizzare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="663ab-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="663ab-108">Procedura: Usare un nome utente personalizzato e il Validator della Password</span><span class="sxs-lookup"><span data-stu-id="663ab-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="663ab-109">Viene dimostrato come integrare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="663ab-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="663ab-110">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="663ab-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="663ab-111">Come ulteriore misura di sicurezza, un client può autenticare il servizio specificando quella prevista *identità* del servizio.</span><span class="sxs-lookup"><span data-stu-id="663ab-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="663ab-112">Se l'identità prevista e l'identità restituita dal servizio non corrispondono, si verifica l'errore di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="663ab-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="663ab-113">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="663ab-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="663ab-114">Viene descritto l'utilizzo della proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> nella classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="663ab-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="663ab-115">Debug degli errori di autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="663ab-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="663ab-116">Vengono analizzati problemi comuni riscontrabili durante l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="663ab-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="663ab-117">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="663ab-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="663ab-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="663ab-118">Related Sections</span></span>  
 [<span data-ttu-id="663ab-119">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="663ab-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="663ab-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="663ab-120">See also</span></span>
- [<span data-ttu-id="663ab-121">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="663ab-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="663ab-122">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="663ab-122">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
