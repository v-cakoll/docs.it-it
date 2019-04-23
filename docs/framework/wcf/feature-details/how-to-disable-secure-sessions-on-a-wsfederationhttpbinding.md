---
title: 'Procedura: Disabilitare sessioni protette in WSFederationHttpBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: 38863cbfe457afd923c3c8238d8c12b4d451c67f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59293956"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a><span data-ttu-id="f703c-102">Procedura: Disabilitare sessioni protette in WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f703c-102">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>
<span data-ttu-id="f703c-103">Alcuni servizi possono richiedere credenziali federate senza tuttavia supportare le sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="f703c-103">Some services may require federated credentials but not support secure sessions.</span></span> <span data-ttu-id="f703c-104">In questo caso occorre disattivare la funzionalità di sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="f703c-104">In that case, you must disable the secure session feature.</span></span> <span data-ttu-id="f703c-105">A differenza della classe <xref:System.ServiceModel.WSHttpBinding>, la classe <xref:System.ServiceModel.WSFederationHttpBinding> non fornisce alcuna modalità di disattivazione delle sessioni protette quando si comunica con un servizio.</span><span class="sxs-lookup"><span data-stu-id="f703c-105">Unlike the <xref:System.ServiceModel.WSHttpBinding>, the <xref:System.ServiceModel.WSFederationHttpBinding> class does not provide a way to disable secure sessions when communicating with a service.</span></span> <span data-ttu-id="f703c-106">È invece necessario creare un'associazione personalizzata che sostituisce le impostazioni della sessione protetta con un bootstrap.</span><span class="sxs-lookup"><span data-stu-id="f703c-106">Instead, you must create a custom binding that replaces the secure session settings with a bootstrap.</span></span>  
  
 <span data-ttu-id="f703c-107">Questo argomento illustra come modificare gli elementi di un'associazione <xref:System.ServiceModel.WSFederationHttpBinding> per creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f703c-107">This topic demonstrates how to modify the binding elements contained within a <xref:System.ServiceModel.WSFederationHttpBinding> to create a custom binding.</span></span> <span data-ttu-id="f703c-108">Il risultato è un'associazione <xref:System.ServiceModel.WSFederationHttpBinding> uguale all'originale in cui tuttavia non vengono utilizzate sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="f703c-108">The result is identical to the <xref:System.ServiceModel.WSFederationHttpBinding> except that it does not use secure sessions.</span></span>  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a><span data-ttu-id="f703c-109">Per creare un'associazione federata personalizzata senza sessioni protette</span><span class="sxs-lookup"><span data-stu-id="f703c-109">To create a custom federated binding without secure session</span></span>  
  
1. <span data-ttu-id="f703c-110">Creare un'istanza della classe <xref:System.ServiceModel.WSFederationHttpBinding> o in modo imperativo nel codice oppure caricando un'associazione di questo tipo dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f703c-110">Create an instance of the <xref:System.ServiceModel.WSFederationHttpBinding> class either imperatively in code or by loading one from the configuration file.</span></span>  
  
2. <span data-ttu-id="f703c-111">Duplicare l'associazione <xref:System.ServiceModel.WSFederationHttpBinding> in un'associazione <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="f703c-111">Clone the <xref:System.ServiceModel.WSFederationHttpBinding> into a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
3. <span data-ttu-id="f703c-112">Individuare l'elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> all'interno dell'associazione <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="f703c-112">Find the <xref:System.ServiceModel.Channels.SecurityBindingElement> in the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
4. <span data-ttu-id="f703c-113">Individuare l'elemento <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> all'interno dell'associazione <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="f703c-113">Find the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> in the <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span></span>  
  
5. <span data-ttu-id="f703c-114">Sostituire l'elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> originale con l'elemento di associazione di sicurezza bootstrap ottenuto dai parametri <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span><span class="sxs-lookup"><span data-stu-id="f703c-114">Replace the original <xref:System.ServiceModel.Channels.SecurityBindingElement> with the bootstrap security binding element from the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f703c-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f703c-115">Example</span></span>  
 <span data-ttu-id="f703c-116">Nell'esempio seguente viene creata un'associazione federata personalizzata senza sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="f703c-116">This following example creates a custom federated binding without secure session.</span></span>  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f703c-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f703c-117">Compiling the Code</span></span>  
  
-   <span data-ttu-id="f703c-118">Per compilare l'esempio di codice, creare un progetto che fa riferimento all'assembly System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="f703c-118">To compile the code example, create a project that references the System.ServiceModel.dll assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f703c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f703c-119">See also</span></span>

- [<span data-ttu-id="f703c-120">Associazioni e sicurezza</span><span class="sxs-lookup"><span data-stu-id="f703c-120">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
