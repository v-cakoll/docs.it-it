---
title: Funzionalità di sicurezza con associazioni personalizzate
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 48d17543f2b133c74bcfa82cfe1a2a0de28b1d01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595193"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="a928f-102">Funzionalità di sicurezza con associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a928f-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="a928f-103">Per eseguire la maggior parte delle attività di sicurezza comuni, è possibile utilizzare una delle associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="a928f-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="a928f-104">Se è necessario un maggiore controllo, tuttavia, è possibile creare un'associazione personalizzata con un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement>, come viene spiegato in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="a928f-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="a928f-105">Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a928f-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a928f-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a928f-106">In This Section</span></span>  
 [<span data-ttu-id="a928f-107">Modalità di autenticazione di SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a928f-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="a928f-108">Vengono descritte le modalità di autenticazione possibili con un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a928f-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="a928f-109">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a928f-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="a928f-110">Vengono descritti i passaggi di base per la creazione di un'associazione personalizzata con un elemento di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a928f-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="a928f-111">Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata</span><span class="sxs-lookup"><span data-stu-id="a928f-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="a928f-112">Viene descritto come creare un elemento di sicurezza per una modalità di autenticazione specificata.</span><span class="sxs-lookup"><span data-stu-id="a928f-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="a928f-113">Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a928f-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="a928f-114">Viene descritto come disattivare sessioni protette durante la creazione di un servizio federativo.</span><span class="sxs-lookup"><span data-stu-id="a928f-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="a928f-115">Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a928f-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="a928f-116">Viene descritto come determinare il verificarsi di un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="a928f-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="a928f-117">Procedura: creare una credenziale di supporto</span><span class="sxs-lookup"><span data-stu-id="a928f-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="a928f-118">Viene descritto come fornire una credenziale di supporto a un servizio, se il servizio lo richiede.</span><span class="sxs-lookup"><span data-stu-id="a928f-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="a928f-119">Procedura: impostare una conferma della firma</span><span class="sxs-lookup"><span data-stu-id="a928f-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="a928f-120">Vengono descritti i passaggi necessari per confermare le firme durante la firma digitale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a928f-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="a928f-121">Procedura: impostare lo sfasamento massimo dei segnali di clock</span><span class="sxs-lookup"><span data-stu-id="a928f-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="a928f-122">Viene descritto come impostare la differenza oraria massima consentita tra un servizio e un client.</span><span class="sxs-lookup"><span data-stu-id="a928f-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="a928f-123">Procedura: disattivare la crittografia delle firme digitali</span><span class="sxs-lookup"><span data-stu-id="a928f-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="a928f-124">Viene descritto come la disattivazione della crittografia di firme digitali possa influire positivamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a928f-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a928f-125">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="a928f-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="a928f-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a928f-126">Related Sections</span></span>  
 [<span data-ttu-id="a928f-127">Informazioni sul livello di protezione</span><span class="sxs-lookup"><span data-stu-id="a928f-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="a928f-128">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="a928f-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="a928f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a928f-129">See also</span></span>

- [<span data-ttu-id="a928f-130">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="a928f-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="a928f-131">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="a928f-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="a928f-132">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="a928f-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
