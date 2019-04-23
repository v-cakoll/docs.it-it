---
title: Funzionalità di sicurezza con associazioni personalizzate
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 25d203fa706eeb0d0ccf1eaf4367ffa5bd7b83aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157274"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="21c46-102">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="21c46-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="21c46-103">Per eseguire la maggior parte delle attività di sicurezza comuni, è possibile utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="21c46-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="21c46-104">Se è necessario un maggiore controllo, tuttavia, è possibile creare un'associazione personalizzata con un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>, come viene spiegato in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="21c46-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="21c46-105">Per altre informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="21c46-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21c46-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="21c46-106">In This Section</span></span>  
 [<span data-ttu-id="21c46-107">Modalità di autenticazione di SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="21c46-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="21c46-108">Vengono descritte le modalità di autenticazione possibili con un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="21c46-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="21c46-109">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="21c46-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="21c46-110">Vengono descritti i passaggi di base per la creazione di un'associazione personalizzata con un elemento di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="21c46-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="21c46-111">Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata</span><span class="sxs-lookup"><span data-stu-id="21c46-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="21c46-112">Viene descritto come creare un elemento di sicurezza per una modalità di autenticazione specificata.</span><span class="sxs-lookup"><span data-stu-id="21c46-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="21c46-113">Procedura: Disabilitare le sessioni protette in un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="21c46-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="21c46-114">Viene descritto come disattivare sessioni protette durante la creazione di un servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="21c46-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="21c46-115">Procedura: Abilitare il rilevamento riproduzione messaggio</span><span class="sxs-lookup"><span data-stu-id="21c46-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="21c46-116">Viene descritto come determinare il verificarsi di un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="21c46-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="21c46-117">Procedura: Creare una credenziale di supporto</span><span class="sxs-lookup"><span data-stu-id="21c46-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="21c46-118">Viene descritto come fornire una credenziale di supporto a un servizio, se il servizio lo richiede.</span><span class="sxs-lookup"><span data-stu-id="21c46-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="21c46-119">Procedura: Configurare una conferma della firma</span><span class="sxs-lookup"><span data-stu-id="21c46-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="21c46-120">Vengono descritti i passaggi necessari per confermare le firme durante la firma digitale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="21c46-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="21c46-121">Procedura: Set un'inclinazione di Clock massima</span><span class="sxs-lookup"><span data-stu-id="21c46-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="21c46-122">Viene descritto come impostare la differenza oraria massima consentita tra un servizio e un client.</span><span class="sxs-lookup"><span data-stu-id="21c46-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="21c46-123">Procedura: Disabilitare la crittografia di firme digitali</span><span class="sxs-lookup"><span data-stu-id="21c46-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="21c46-124">Viene descritto come la disattivazione della crittografia di firme digitali possa influire positivamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="21c46-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="21c46-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="21c46-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="21c46-126">\<security></span><span class="sxs-lookup"><span data-stu-id="21c46-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="21c46-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="21c46-127">Related Sections</span></span>  
 [<span data-ttu-id="21c46-128">Informazioni sul livello di protezione</span><span class="sxs-lookup"><span data-stu-id="21c46-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="21c46-129">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="21c46-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="21c46-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21c46-130">See also</span></span>

- [<span data-ttu-id="21c46-131">Associazioni e sicurezza</span><span class="sxs-lookup"><span data-stu-id="21c46-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [<span data-ttu-id="21c46-132">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="21c46-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="21c46-133">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="21c46-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
