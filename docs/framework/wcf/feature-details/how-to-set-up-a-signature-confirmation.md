---
title: 'Procedura: Impostare una conferma della firma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 56e8720a6130d2908fbfb83bd243a54fae9a2406
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315816"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="2c3f0-102">Procedura: Impostare una conferma della firma</span><span class="sxs-lookup"><span data-stu-id="2c3f0-102">How to: Set Up a Signature Confirmation</span></span>
<span data-ttu-id="2c3f0-103">*Conferma della firma* è un meccanismo iniziatore del messaggio garantire che una risposta ricevuta sia stata generata in risposta al messaggio originale del mittente.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="2c3f0-104">La conferma della firma è definita nella specifica WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="2c3f0-105">Se un endpoint supporta WS-Security 1.0, non è possibile utilizzare la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>  
  
 <span data-ttu-id="2c3f0-106">Nelle procedure seguenti viene illustrato come consentire la conferma della firma utilizzando un <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="2c3f0-107">È possibile utilizzare la stessa procedura con un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="2c3f0-108">La procedura è basata sui passaggi di base illustrati [come: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="2c3f0-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="2c3f0-109">Per consentire la conferma della firma nel codice</span><span class="sxs-lookup"><span data-stu-id="2c3f0-109">To enable signature confirmation in code</span></span>  
  
1. <span data-ttu-id="2c3f0-110">Creare un'istanza della classe <xref:System.ServiceModel.Channels.BindingElementCollection>.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>  
  
2. <span data-ttu-id="2c3f0-111">Creare un'istanza di <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> classe.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>  
  
3. <span data-ttu-id="2c3f0-112">Impostare <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="2c3f0-113">Aggiungere l'elemento di sicurezza alla raccolta di associazioni.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-113">Add the security element to the binding collection.</span></span>  
  
5. <span data-ttu-id="2c3f0-114">Creare un'associazione personalizzata, come specificato in [come: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="2c3f0-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="2c3f0-115">Per consentire la conferma della firma nella configurazione</span><span class="sxs-lookup"><span data-stu-id="2c3f0-115">To enable signature confirmation in configuration</span></span>  
  
1. <span data-ttu-id="2c3f0-116">Aggiungere un elemento `<customBinding>` alla sezione`<bindings>` del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>  
  
2. <span data-ttu-id="2c3f0-117">Aggiungere un elemento `<binding>` e impostare l'attributo del nome su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="2c3f0-118">Aggiungere un elemento di codifica appropriato.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="2c3f0-119">Nell'esempio seguente viene aggiunto un elemento `<TextMessageEncoding>`.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-119">The following example adds a `<TextMessageEncoding>` element.</span></span>  
  
4. <span data-ttu-id="2c3f0-120">Aggiungere un elemento figlio  `<security>`requireSignatureConfirmation e impostare l'attributo`requireSignatureConfirmation`true su`true`.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>  
  
5. <span data-ttu-id="2c3f0-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-121">Optional.</span></span> <span data-ttu-id="2c3f0-122">Per consentire la conferma della firma durante il bootstrap, aggiungere un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento figlio e impostare il `equireSignatureConfirmation` attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `equireSignatureConfirmation` attribute to `true`.</span></span>  
  
6. <span data-ttu-id="2c3f0-123">Aggiungere un elemento di trasporto appropriato.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-123">Add an appropriate transport element.</span></span> <span data-ttu-id="2c3f0-124">L'esempio seguente aggiunge un' [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span><span class="sxs-lookup"><span data-stu-id="2c3f0-124">The following example adds an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a><span data-ttu-id="2c3f0-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c3f0-125">Example</span></span>  
 <span data-ttu-id="2c3f0-126">Nel codice seguente viene creata un'istanza di <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> e viene impostata la proprietà <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="2c3f0-127">Si noti che in questo esempio non viene utilizzato l'elemento `<secureConversationBootstrap>` illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="2c3f0-128">In questo esempio viene illustrata la conferma della firma quando si utilizza un token di Windows (protocollo Kerberos).</span><span class="sxs-lookup"><span data-stu-id="2c3f0-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="2c3f0-129">In questo caso, la firma del client viene restituita in tutte le risposte dal servizio e viene confermata dal client.</span><span class="sxs-lookup"><span data-stu-id="2c3f0-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2c3f0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c3f0-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="2c3f0-131">Procedura: Creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2c3f0-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2c3f0-132">Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata</span><span class="sxs-lookup"><span data-stu-id="2c3f0-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
