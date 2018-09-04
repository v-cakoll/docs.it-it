---
title: Scenari di sicurezza comuni
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 220795488d6e4bedf40e0764040470c18d3a3b48
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525824"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="70463-102">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="70463-102">Common Security Scenarios</span></span>
<span data-ttu-id="70463-103">Negli argomenti di questa sezione vengono illustrate alcune possibili configurazioni di sicurezza del client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="70463-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="70463-104">Le configurazioni dipendono da alcuni fattori.</span><span class="sxs-lookup"><span data-stu-id="70463-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="70463-105">Variano, ad esempio, a seconda che un servizio o un client sia su una Intranet, o a seconda che la protezione sia fornita da Windows o da un trasporto, ad esempio HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70463-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70463-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="70463-106">In This Section</span></span>  
 [<span data-ttu-id="70463-107">Client e servizio non protetti in Internet</span><span class="sxs-lookup"><span data-stu-id="70463-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="70463-108">Esempio di un client e di un servizio pubblico non protetti.</span><span class="sxs-lookup"><span data-stu-id="70463-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="70463-109">Client e servizio non protetti nella rete Intranet</span><span class="sxs-lookup"><span data-stu-id="70463-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="70463-110">Un servizio Windows Communication Foundation (WCF) di base sviluppato per fornire informazioni su una rete privata protetta a un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="70463-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="70463-111">Sicurezza del trasporto con autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="70463-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="70463-112">L'applicazione consente ai client di accedere utilizzando l'autenticazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="70463-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="70463-113">Sicurezza del trasporto con autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="70463-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="70463-114">Vengono illustrati un client e un servizio protetti dalla protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="70463-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="70463-115">Sicurezza del trasporto con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="70463-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="70463-116">In questo scenario viene utilizzata la protezione del trasporto, ad esempio HTTPS, per garantire riservatezza e integrità.</span><span class="sxs-lookup"><span data-stu-id="70463-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="70463-117">Sicurezza del trasporto con autenticazione del certificato</span><span class="sxs-lookup"><span data-stu-id="70463-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="70463-118">Vengono illustrati un client e un servizio protetti da un certificato.</span><span class="sxs-lookup"><span data-stu-id="70463-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="70463-119">Sicurezza dei messaggi con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="70463-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="70463-120">Vengono illustrati un client e servizio protetti dalla protezione dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="70463-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="70463-121">Sicurezza dei messaggi con un client con tipo di credenziale UserName</span><span class="sxs-lookup"><span data-stu-id="70463-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="70463-122">Il client è un'applicazione Windows Forms che consente ai client di accedere utilizzando un nome utente e una password del dominio.</span><span class="sxs-lookup"><span data-stu-id="70463-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="70463-123">Sicurezza dei messaggi con un certificato client</span><span class="sxs-lookup"><span data-stu-id="70463-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="70463-124">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="70463-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="70463-125">Un contesto di sicurezza viene stabilito tramite la negoziazione Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="70463-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="70463-126">Sicurezza dei messaggi con un client Windows</span><span class="sxs-lookup"><span data-stu-id="70463-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="70463-127">Variazione del client del certificato.</span><span class="sxs-lookup"><span data-stu-id="70463-127">A variation of the certificate client.</span></span> <span data-ttu-id="70463-128">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="70463-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="70463-129">Un contesto di sicurezza viene stabilito tramite la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="70463-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="70463-130">Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="70463-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="70463-131">Vengono illustrati un client e un servizio protetti da un dominio Kerberos.</span><span class="sxs-lookup"><span data-stu-id="70463-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="70463-132">Sicurezza dei messaggi con autenticazione reciproca dei certificati</span><span class="sxs-lookup"><span data-stu-id="70463-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="70463-133">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="70463-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="70463-134">Il certificato server viene distribuito con l'applicazione ed è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="70463-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="70463-135">Sicurezza dei messaggi con token rilasciati</span><span class="sxs-lookup"><span data-stu-id="70463-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="70463-136">Protezione federata che consente di stabilire una relazione di trust tra domini indipendenti.</span><span class="sxs-lookup"><span data-stu-id="70463-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="70463-137">Sottosistema attendibile</span><span class="sxs-lookup"><span data-stu-id="70463-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="70463-138">Un client accede a uno o più servizi Web distribuiti in una rete.</span><span class="sxs-lookup"><span data-stu-id="70463-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="70463-139">I servizi Web accedono a risorse aggiuntive, ad esempio database o altri servizi Web, che devono essere protette.</span><span class="sxs-lookup"><span data-stu-id="70463-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="70463-140">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="70463-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="70463-141">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="70463-141">Related Sections</span></span>  
 [<span data-ttu-id="70463-142">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70463-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="70463-143">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="70463-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="70463-144">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="70463-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="70463-145">Associazioni e sicurezza</span><span class="sxs-lookup"><span data-stu-id="70463-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="70463-146">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="70463-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="70463-147">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="70463-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="70463-148">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70463-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="70463-149">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="70463-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="70463-150">Controllo</span><span class="sxs-lookup"><span data-stu-id="70463-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="70463-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70463-151">See Also</span></span>  
 [<span data-ttu-id="70463-152">Linee guida e procedure consigliate per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="70463-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [<span data-ttu-id="70463-153">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="70463-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
