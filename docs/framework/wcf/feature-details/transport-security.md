---
title: Sicurezza trasporto
description: Usare questi riferimenti per comprendere i meccanismi di sicurezza del trasporto in WFC, il modo in cui vengono implementati e le relative opzioni.
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
ms.openlocfilehash: d39aa49906b79b9e12eecf04629080863719f986
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244751"
---
# <a name="transport-security"></a><span data-ttu-id="c436f-103">Sicurezza trasporto</span><span class="sxs-lookup"><span data-stu-id="c436f-103">Transport Security</span></span>
<span data-ttu-id="c436f-104">La sicurezza del trasporto in Windows Communication Foundation (WCF) dipende dall'associazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="c436f-104">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="c436f-105">Il trasporto implementato dall'associazione determina l'effettivo meccanismo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c436f-105">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="c436f-106">Negli argomenti contenuti in questa sezione sono illustrati i meccanismi implementati e le rispettive opzioni.</span><span class="sxs-lookup"><span data-stu-id="c436f-106">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c436f-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c436f-107">In This Section</span></span>  
 [<span data-ttu-id="c436f-108">Panoramica sulla sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="c436f-108">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="c436f-109">Vengono illustrati i concetti di base della sicurezza del trasporto in WCF.</span><span class="sxs-lookup"><span data-stu-id="c436f-109">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="c436f-110">Protezione del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="c436f-110">HTTP Transport Security</span></span>](http-transport-security.md)  
 <span data-ttu-id="c436f-111">Viene illustrato il modo in cui WCF implementa Secure Sockets Layer (SSL o HTTPS).</span><span class="sxs-lookup"><span data-stu-id="c436f-111">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="c436f-112">Informazioni sull'autenticazione HTTP</span><span class="sxs-lookup"><span data-stu-id="c436f-112">Understanding HTTP Authentication</span></span>](understanding-http-authentication.md)  
 <span data-ttu-id="c436f-113">Vengono descritti gli schemi di autenticazione HTTP, ad esempio di base, digest, NT LAN Manager (NTLM) e altri.</span><span class="sxs-lookup"><span data-stu-id="c436f-113">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="c436f-114">Utilizzo della rappresentazione con la sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="c436f-114">Using Impersonation with Transport Security</span></span>](using-impersonation-with-transport-security.md)  
 <span data-ttu-id="c436f-115">Vengono spiegati i cinque livelli di rappresentazione possibili con la modalità di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="c436f-115">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="c436f-116">Procedura: configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="c436f-116">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="c436f-117">Vengono illustrate le nozioni di base della configurazione di una porta in un computer con un certificato X.509 per la protezione del trasporto SSL.</span><span class="sxs-lookup"><span data-stu-id="c436f-117">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c436f-118">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="c436f-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="c436f-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c436f-119">Related Sections</span></span>  
 [<span data-ttu-id="c436f-120">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="c436f-120">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="c436f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c436f-121">See also</span></span>

- [<span data-ttu-id="c436f-122">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="c436f-122">Programming WCF Security</span></span>](programming-wcf-security.md)
