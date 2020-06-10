---
title: Scenari di sicurezza comuni
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: f36ebdb5ea248ec8134c688f89eb5d0be38dfe38
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579736"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="b8bbd-102">Scenari di sicurezza comuni</span><span class="sxs-lookup"><span data-stu-id="b8bbd-102">Common Security Scenarios</span></span>
<span data-ttu-id="b8bbd-103">Negli argomenti di questa sezione vengono illustrate alcune possibili configurazioni di sicurezza del client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="b8bbd-104">Le configurazioni dipendono da alcuni fattori.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="b8bbd-105">Variano, ad esempio, a seconda che un servizio o un client sia su una Intranet, o a seconda che la protezione sia fornita da Windows o da un trasporto, ad esempio HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8bbd-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b8bbd-106">In This Section</span></span>  
 [<span data-ttu-id="b8bbd-107">Client e servizio non protetti in Internet</span><span class="sxs-lookup"><span data-stu-id="b8bbd-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="b8bbd-108">Esempio di un client e di un servizio pubblico non protetti.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="b8bbd-109">Client e servizio Intranet non protetti</span><span class="sxs-lookup"><span data-stu-id="b8bbd-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="b8bbd-110">Un servizio Basic Windows Communication Foundation (WCF) sviluppato per fornire informazioni su una rete privata protetta a un'applicazione WCF.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="b8bbd-111">Protezione del trasporto con l'autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="b8bbd-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="b8bbd-112">L'applicazione consente ai client di accedere utilizzando l'autenticazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="b8bbd-113">Protezione del trasporto con l'autenticazione di Windows</span><span class="sxs-lookup"><span data-stu-id="b8bbd-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="b8bbd-114">Vengono illustrati un client e un servizio protetti dalla protezione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="b8bbd-115">Sicurezza del trasporto con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="b8bbd-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="b8bbd-116">In questo scenario viene utilizzata la protezione del trasporto, ad esempio HTTPS, per garantire riservatezza e integrità.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="b8bbd-117">Sicurezza del trasporto con autenticazione del certificato</span><span class="sxs-lookup"><span data-stu-id="b8bbd-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="b8bbd-118">Vengono illustrati un client e un servizio protetti da un certificato.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="b8bbd-119">Protezione dei messaggi con un client anonimo</span><span class="sxs-lookup"><span data-stu-id="b8bbd-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="b8bbd-120">Mostra un client e un servizio protetti dalla sicurezza dei messaggi WCF.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="b8bbd-121">Protezione dei messaggi tramite client con tipo di credenziale UserName</span><span class="sxs-lookup"><span data-stu-id="b8bbd-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="b8bbd-122">Il client è un'applicazione Windows Form che consente ai client di accedere utilizzando un nome utente e una password del dominio.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="b8bbd-123">Protezione dei messaggi con un client di certificato</span><span class="sxs-lookup"><span data-stu-id="b8bbd-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="b8bbd-124">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b8bbd-125">Un contesto di sicurezza viene stabilito tramite la negoziazione Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="b8bbd-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="b8bbd-126">Protezione dei messaggi con un client Windows</span><span class="sxs-lookup"><span data-stu-id="b8bbd-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="b8bbd-127">Variazione del client del certificato.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-127">A variation of the certificate client.</span></span> <span data-ttu-id="b8bbd-128">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b8bbd-129">Un contesto di sicurezza viene stabilito tramite la negoziazione TLS.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="b8bbd-130">Sicurezza dei messaggi con un client Windows senza negoziazione delle credenziali</span><span class="sxs-lookup"><span data-stu-id="b8bbd-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="b8bbd-131">Vengono illustrati un client e un servizio protetti da un dominio Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="b8bbd-132">Protezione dei messaggi con certificati reciproci</span><span class="sxs-lookup"><span data-stu-id="b8bbd-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="b8bbd-133">I server hanno i certificati e ogni client ne ha uno.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="b8bbd-134">Il certificato server viene distribuito con l'applicazione ed è disponibile fuori banda.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="b8bbd-135">Protezione a livello di messaggio con il client token emessi</span><span class="sxs-lookup"><span data-stu-id="b8bbd-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="b8bbd-136">Protezione federata che consente di stabilire una relazione di trust tra domini indipendenti.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="b8bbd-137">Sottosistema attendibile</span><span class="sxs-lookup"><span data-stu-id="b8bbd-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="b8bbd-138">Un client accede a uno o più servizi Web distribuiti in una rete.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="b8bbd-139">I servizi Web accedono a risorse aggiuntive, ad esempio database o altri servizi Web, che devono essere protette.</span><span class="sxs-lookup"><span data-stu-id="b8bbd-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b8bbd-140">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="b8bbd-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="b8bbd-141">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b8bbd-141">Related Sections</span></span>  
 [<span data-ttu-id="b8bbd-142">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b8bbd-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="b8bbd-143">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="b8bbd-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="b8bbd-144">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b8bbd-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="b8bbd-145">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="b8bbd-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="b8bbd-146">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="b8bbd-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="b8bbd-147">autenticazione</span><span class="sxs-lookup"><span data-stu-id="b8bbd-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="b8bbd-148">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b8bbd-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="b8bbd-149">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="b8bbd-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="b8bbd-150">Controllo</span><span class="sxs-lookup"><span data-stu-id="b8bbd-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="b8bbd-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8bbd-151">See also</span></span>

- [<span data-ttu-id="b8bbd-152">Indicazioni di sicurezza e procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b8bbd-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="b8bbd-153">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b8bbd-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
