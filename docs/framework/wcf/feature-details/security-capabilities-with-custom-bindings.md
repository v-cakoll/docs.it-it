---
title: "Funzionalità di sicurezza con associazioni personalizzate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9d252dca363c952dde44b499363e285d4bb7eb82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="22336-102">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="22336-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="22336-103">Per eseguire la maggior parte delle attività di sicurezza comuni, è possibile utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="22336-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="22336-104">Se è necessario un maggiore controllo, tuttavia, è possibile creare un'associazione personalizzata con un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>, come viene spiegato in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="22336-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="22336-105">associazioni personalizzate, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="22336-105"> custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22336-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="22336-106">In This Section</span></span>  
 [<span data-ttu-id="22336-107">Modalità di autenticazione di SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="22336-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="22336-108">Vengono descritte le modalità di autenticazione possibili con un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="22336-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="22336-109">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="22336-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="22336-110">Vengono descritti i passaggi di base per la creazione di un'associazione personalizzata con un elemento di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="22336-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="22336-111">Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificato</span><span class="sxs-lookup"><span data-stu-id="22336-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="22336-112">Viene descritto come creare un elemento di sicurezza per una modalità di autenticazione specificata.</span><span class="sxs-lookup"><span data-stu-id="22336-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="22336-113">Procedura: disattivare sessioni protette in una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="22336-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="22336-114">Viene descritto come disattivare sessioni protette durante la creazione di un servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="22336-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="22336-115">Procedura: abilitare il rilevamento riproduzione messaggio</span><span class="sxs-lookup"><span data-stu-id="22336-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="22336-116">Viene descritto come determinare il verificarsi di un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="22336-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="22336-117">Procedura: creare una credenziale di supporto</span><span class="sxs-lookup"><span data-stu-id="22336-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="22336-118">Viene descritto come fornire una credenziale di supporto a un servizio, se il servizio lo richiede.</span><span class="sxs-lookup"><span data-stu-id="22336-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="22336-119">Procedura: impostare una conferma della firma</span><span class="sxs-lookup"><span data-stu-id="22336-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="22336-120">Vengono descritti i passaggi necessari per confermare le firme durante la firma digitale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="22336-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="22336-121">Procedura: impostare un numero massimo di sfasamento</span><span class="sxs-lookup"><span data-stu-id="22336-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="22336-122">Viene descritto come impostare la differenza oraria massima consentita tra un servizio e un client.</span><span class="sxs-lookup"><span data-stu-id="22336-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="22336-123">Procedura: disabilitare la crittografia di firme digitali</span><span class="sxs-lookup"><span data-stu-id="22336-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="22336-124">Viene descritto come la disattivazione della crittografia di firme digitali possa influire positivamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="22336-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="22336-125">Riferimento</span><span class="sxs-lookup"><span data-stu-id="22336-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="22336-126">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="22336-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="22336-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="22336-127">Related Sections</span></span>  
 [<span data-ttu-id="22336-128">Informazioni sul livello di protezione</span><span class="sxs-lookup"><span data-stu-id="22336-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="22336-129">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="22336-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="22336-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22336-130">See Also</span></span>  
 [<span data-ttu-id="22336-131">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="22336-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="22336-132">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="22336-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="22336-133">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="22336-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
