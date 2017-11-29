---
title: Scenari di sicurezza comuni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9428c5d7c8c6cf0f571b05a8b9c33b96d073d7a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="common-security-scenarios"></a><span data-ttu-id="88a37-102">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="88a37-102">Common Security Scenarios</span></span>
<span data-ttu-id="88a37-103">Negli argomenti di questa sezione vengono illustrate alcune possibili configurazioni di sicurezza del client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="88a37-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="88a37-104">Le configurazioni dipendono da alcuni fattori.</span><span class="sxs-lookup"><span data-stu-id="88a37-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="88a37-105">Variano, ad esempio, a seconda che un servizio o un client sia su una Intranet, o a seconda che la protezione sia fornita da Windows o da un trasporto, ad esempio HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88a37-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88a37-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="88a37-106">In This Section</span></span>  
 [<span data-ttu-id="88a37-107">Servizio e il Client non protetta di Internet</span><span class="sxs-lookup"><span data-stu-id="88a37-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="88a37-108">Esempio di un client e di un servizio pubblico non protetti.</span><span class="sxs-lookup"><span data-stu-id="88a37-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="88a37-109">Servizio intranet Client e non protetti</span><span class="sxs-lookup"><span data-stu-id="88a37-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="88a37-110">Un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] di base sviluppato per fornire informazioni su una rete privata protetta a un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88a37-110">A basic [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span>  
  
 [<span data-ttu-id="88a37-111">Sicurezza del trasporto con l'autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="88a37-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="88a37-112">L'applicazione consente ai client di accedere utilizzando l'autenticazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="88a37-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="88a37-113">Sicurezza del trasporto con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="88a37-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="88a37-114">Vengono illustrati un client e un servizio protetti dalla protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="88a37-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="88a37-115">Sicurezza del trasporto con un Client anonimo</span><span class="sxs-lookup"><span data-stu-id="88a37-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="88a37-116">In questo scenario viene utilizzata la protezione del trasporto, ad esempio HTTPS, per garantire riservatezza e integrità.</span><span class="sxs-lookup"><span data-stu-id="88a37-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="88a37-117">Sicurezza del trasporto con l'autenticazione del certificato</span><span class="sxs-lookup"><span data-stu-id="88a37-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="88a37-118">Vengono illustrati un client e un servizio protetti da un certificato.</span><span class="sxs-lookup"><span data-stu-id="88a37-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="88a37-119">Sicurezza dei messaggi con un Client anonimo</span><span class="sxs-lookup"><span data-stu-id="88a37-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="88a37-120">Vengono illustrati un client e un servizio protetti dalla protezione dei messaggi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88a37-120">Shows a client and service secured by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message security.</span></span>  
  
 [<span data-ttu-id="88a37-121">Sicurezza dei messaggi con un Client di nome utente</span><span class="sxs-lookup"><span data-stu-id="88a37-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="88a37-122">Il client è un'applicazione Windows Forms che consente ai client di accedere utilizzando un nome utente e una password del dominio.</span><span class="sxs-lookup"><span data-stu-id="88a37-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="88a37-123">Sicurezza dei messaggi con un Client dei certificati</span><span class="sxs-lookup"><span data-stu-id="88a37-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="88a37-124">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="88a37-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="88a37-125">Un contesto di sicurezza viene stabilito tramite la negoziazione Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="88a37-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="88a37-126">Sicurezza dei messaggi con un Client Windows</span><span class="sxs-lookup"><span data-stu-id="88a37-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="88a37-127">Variazione del client del certificato.</span><span class="sxs-lookup"><span data-stu-id="88a37-127">A variation of the certificate client.</span></span> <span data-ttu-id="88a37-128">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="88a37-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="88a37-129">Un contesto di sicurezza viene stabilito tramite la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="88a37-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="88a37-130">Sicurezza dei messaggi con un Client di Windows senza negoziazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="88a37-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="88a37-131">Vengono illustrati un client e un servizio protetti da un dominio Kerberos.</span><span class="sxs-lookup"><span data-stu-id="88a37-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="88a37-132">Sicurezza dei messaggi con certificati reciproci</span><span class="sxs-lookup"><span data-stu-id="88a37-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="88a37-133">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="88a37-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="88a37-134">Il certificato server viene distribuito con l'applicazione ed è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="88a37-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="88a37-135">Sicurezza dei messaggi con i token emessi</span><span class="sxs-lookup"><span data-stu-id="88a37-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="88a37-136">Protezione federata che consente di stabilire una relazione di trust tra domini indipendenti.</span><span class="sxs-lookup"><span data-stu-id="88a37-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="88a37-137">Sottosistema attendibile</span><span class="sxs-lookup"><span data-stu-id="88a37-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="88a37-138">Un client accede a uno o più servizi Web distribuiti in una rete.</span><span class="sxs-lookup"><span data-stu-id="88a37-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="88a37-139">I servizi Web accedono a risorse aggiuntive, ad esempio database o altri servizi Web, che devono essere protette.</span><span class="sxs-lookup"><span data-stu-id="88a37-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="88a37-140">Riferimento</span><span class="sxs-lookup"><span data-stu-id="88a37-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="88a37-141">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="88a37-141">Related Sections</span></span>  
 [<span data-ttu-id="88a37-142">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="88a37-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="88a37-143">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="88a37-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="88a37-144">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="88a37-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="88a37-145">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="88a37-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="88a37-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="88a37-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="88a37-147">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="88a37-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="88a37-148">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="88a37-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="88a37-149">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="88a37-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="88a37-150">Il controllo</span><span class="sxs-lookup"><span data-stu-id="88a37-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="88a37-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88a37-151">See Also</span></span>  
 [<span data-ttu-id="88a37-152">Guida alla protezione e le procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="88a37-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [<span data-ttu-id="88a37-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="88a37-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
