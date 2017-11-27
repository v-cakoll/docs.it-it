---
title: Protezione del trasporto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: d9576321ca44d568633fcba40e56f9582d3f5db5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transport-security"></a><span data-ttu-id="e1a6c-102">Protezione del trasporto</span><span class="sxs-lookup"><span data-stu-id="e1a6c-102">Transport Security</span></span>
<span data-ttu-id="e1a6c-103">La protezione del trasporto in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] dipende dall'associazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-103">Transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depends on the binding selected.</span></span> <span data-ttu-id="e1a6c-104">Il trasporto implementato dall'associazione determina l'effettivo meccanismo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="e1a6c-105">Negli argomenti contenuti in questa sezione sono illustrati i meccanismi implementati e le rispettive opzioni.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1a6c-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e1a6c-106">In This Section</span></span>  
 [<span data-ttu-id="e1a6c-107">Panoramica della sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="e1a6c-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="e1a6c-108">Vengono spiegate le nozioni di base della protezione del trasporto in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1a6c-108">Explains the basics of transport security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="e1a6c-109">Sicurezza del trasporto HTTP</span><span class="sxs-lookup"><span data-stu-id="e1a6c-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="e1a6c-110">Viene spiegato come in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia implementato Secure Sockets Layer (SSL o HTTPS).</span><span class="sxs-lookup"><span data-stu-id="e1a6c-110">Explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="e1a6c-111">Informazioni sull'autenticazione HTTP</span><span class="sxs-lookup"><span data-stu-id="e1a6c-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="e1a6c-112">Vengono descritti gli schemi di autenticazione HTTP, ad esempio di base, digest, NT LAN Manager (NTLM) e altri.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="e1a6c-113">Utilizzo della rappresentazione con la sicurezza del trasporto</span><span class="sxs-lookup"><span data-stu-id="e1a6c-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="e1a6c-114">Vengono spiegati i cinque livelli di rappresentazione possibili con la modalità di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="e1a6c-115">Procedura: configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="e1a6c-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="e1a6c-116">Vengono illustrate le nozioni di base della configurazione di una porta in un computer con un certificato X.509 per la protezione del trasporto SSL.</span><span class="sxs-lookup"><span data-stu-id="e1a6c-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e1a6c-117">Riferimento</span><span class="sxs-lookup"><span data-stu-id="e1a6c-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="e1a6c-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e1a6c-118">Related Sections</span></span>  
 [<span data-ttu-id="e1a6c-119">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e1a6c-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1a6c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1a6c-120">See Also</span></span>  
 [<span data-ttu-id="e1a6c-121">Programmazione della sicurezza WCF</span><span class="sxs-lookup"><span data-stu-id="e1a6c-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
