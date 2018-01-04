---
title: 'Procedura: creare un token di contesto di sicurezza per una sessione sicura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3dc0e44e7f561e39128e32d3af5fbd495316fdd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="13eaf-102">Procedura: creare un token di contesto di sicurezza per una sessione sicura</span><span class="sxs-lookup"><span data-stu-id="13eaf-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="13eaf-103">Per evitare la perdita di una determinata sessione protetta quando il servizio viene riciclato, è possibile utilizzare in tale sessione un token di contesto di sicurezza (SCT, Security Context Token) con stato.</span><span class="sxs-lookup"><span data-stu-id="13eaf-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="13eaf-104">Ad esempio, quando in una sessione protetta si utilizza un token SCT senza stato e si reimposta Internet Information Services (IIS), i dati di sessione associati al servizio vengono persi.</span><span class="sxs-lookup"><span data-stu-id="13eaf-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="13eaf-105">Questi dati di sessione comprendono una cache del token SCT.</span><span class="sxs-lookup"><span data-stu-id="13eaf-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="13eaf-106">Pertanto, quando un client invia al servizio un token SCT senza stato, viene restituito un errore, in quanto risulta impossibile recuperare la chiave associata al token SCT.</span><span class="sxs-lookup"><span data-stu-id="13eaf-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="13eaf-107">Se tuttavia si utilizza un token SCT con stato, la relativa chiave associata è contenuta nel token SCT</span><span class="sxs-lookup"><span data-stu-id="13eaf-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="13eaf-108">e quindi nel messaggio. Ne consegue che in questo caso il riciclo del servizio non influisce sulla sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="13eaf-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="13eaf-109">Per impostazione predefinita, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizza token SCT senza stato nelle sessioni protette.</span><span class="sxs-lookup"><span data-stu-id="13eaf-109">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="13eaf-110">In questo argomento viene descritto in modo dettagliato come utilizzare token SCT con stato in una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="13eaf-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13eaf-111">I token SCT con stato non possono essere utilizzati in una sessione protetta che prevede un contratto derivato dall'interfaccia <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="13eaf-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13eaf-112">Nelle applicazioni che utilizzano token SCT con stato in una sessione protetta, l'ID del thread del servizio deve essere un account utente a cui è stato associato un profilo utente.</span><span class="sxs-lookup"><span data-stu-id="13eaf-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="13eaf-113">Quando il servizio viene eseguito nel contesto di un account privo di profilo utente, ad esempio `Local Service`, è possibile che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="13eaf-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13eaf-114">Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token SCT con stato.</span><span class="sxs-lookup"><span data-stu-id="13eaf-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="13eaf-115">Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="13eaf-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="13eaf-116">[Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-116"> [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="13eaf-117">Per usare token SCT con stato in una sessione protetta</span><span class="sxs-lookup"><span data-stu-id="13eaf-117">To use stateful SCTs in a secure session</span></span>  
  
-   <span data-ttu-id="13eaf-118">Creare un'associazione personalizzata che prevede la protezione dei messaggi SOAP mediante una sessione protetta che utilizza un token SCT con stato.</span><span class="sxs-lookup"><span data-stu-id="13eaf-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1.  <span data-ttu-id="13eaf-119">Definire un'associazione personalizzata, aggiungendo un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) al file di configurazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="13eaf-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  <span data-ttu-id="13eaf-120">Aggiungere un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento figlio di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-120">Add a [\<binding>](../../../../docs/framework/misc/binding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="13eaf-121">Specificare il nome dell'associazione impostando l'attributo `name` su un nome univoco all'interno del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13eaf-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  <span data-ttu-id="13eaf-122">Specificare la modalità di autenticazione per i messaggi inviati da e verso il servizio mediante l'aggiunta di un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento figlio di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="13eaf-123">Specificare l'utilizzo di una sessione protetta impostando l'attributo `authenticationMode` su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="13eaf-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="13eaf-124">Specificare l'utilizzo di token SCT con stato impostando l'attributo `requireSecurityContextCancellation` su `false`.</span><span class="sxs-lookup"><span data-stu-id="13eaf-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  <span data-ttu-id="13eaf-125">Specificare la modalità di autenticazione il client durante la sessione protetta viene stabilita mediante l'aggiunta di un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento figlio di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="13eaf-126">Specificare la modalità di autenticazione del client impostando l'attributo `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="13eaf-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  <span data-ttu-id="13eaf-127">Specificare la codifica dei messaggi tramite l'aggiunta di un elemento di codifica, ad esempio [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  <span data-ttu-id="13eaf-128">Specificare il trasporto tramite l'aggiunta di un elemento di trasporto, ad esempio il [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span><span class="sxs-lookup"><span data-stu-id="13eaf-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="13eaf-129">Nell'esempio di codice seguente si utilizza la configurazione per specificare un'associazione personalizzata in cui i messaggi possono utilizzare token SCT con stato in una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="13eaf-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="13eaf-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="13eaf-130">Example</span></span>  
 <span data-ttu-id="13eaf-131">Nell'esempio di codice seguente viene creata un'associazione personalizzata che usa la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> per l'avvio automatico di una sessione protetta.</span><span class="sxs-lookup"><span data-stu-id="13eaf-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="13eaf-132">Quando si utilizza l'autenticazione di Windows insieme ai token SCT con stato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] imposta la proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> su anonimo anziché popolarla con l'ID del chiamante effettivo.</span><span class="sxs-lookup"><span data-stu-id="13eaf-132">When Windows authentication is used in combination with a stateful SCT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="13eaf-133">Poiché il sistema di sicurezza di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deve ricreare il contenuto del contesto di sicurezza del servizio per ogni richiesta contenuta nel token SCT in ingresso, il server non memorizza alcuna traccia relativa alla sessione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="13eaf-133">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="13eaf-134">Inoltre, poiché è impossibile serializzare l'istanza della classe <xref:System.Security.Principal.WindowsIdentity> nel token SCT, la proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> restituisce un'identità anonima.</span><span class="sxs-lookup"><span data-stu-id="13eaf-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="13eaf-135">Questo comportamento viene illustrato nella configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="13eaf-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="13eaf-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13eaf-136">See Also</span></span>  
 [<span data-ttu-id="13eaf-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="13eaf-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
