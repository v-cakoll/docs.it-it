---
title: "Procedura: Creare un'associazione federata duplex"
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346236"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="c417d-102">Procedura: Creare un'associazione federata duplex</span><span class="sxs-lookup"><span data-stu-id="c417d-102">How to: Create a Duplex Federated Binding</span></span>
<xref:System.ServiceModel.WSFederationHttpBinding> <span data-ttu-id="c417d-103">supporta solo i contratti di scambio di messaggi datagrammi e di tipo request/reply.</span><span class="sxs-lookup"><span data-stu-id="c417d-103">only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="c417d-104">Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c417d-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="c417d-105">Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="c417d-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="c417d-106">Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.</span><span class="sxs-lookup"><span data-stu-id="c417d-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="c417d-107">È inoltre possibile creare l'associazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="c417d-107">You can also create the binding in code.</span></span> <span data-ttu-id="c417d-108">Per una descrizione dello stack di elementi di associazione per creare, vedere [come: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="c417d-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="c417d-109">Per creare un'associazione personalizzata federata duplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="c417d-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="c417d-110">Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="c417d-111">All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="c417d-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="c417d-112">All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c417d-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c417d-113">All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c417d-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c417d-114">Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="c417d-115">Seguendo la [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento, creare un oggetto vuoto [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="c417d-116">Seguendo la [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, creare un oggetto vuoto [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="c417d-117">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP</span><span class="sxs-lookup"><span data-stu-id="c417d-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="c417d-118">Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="c417d-119">All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="c417d-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="c417d-120">All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c417d-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c417d-121">All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c417d-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c417d-122">Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="c417d-123">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP</span><span class="sxs-lookup"><span data-stu-id="c417d-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="c417d-124">Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="c417d-125">All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="c417d-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="c417d-126">All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="c417d-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="c417d-127">All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="c417d-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="c417d-128">Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="c417d-129">Seguendo la [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, creare un oggetto vuoto [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c417d-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="c417d-130">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="c417d-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="c417d-131">Esempio con 3 associazioni</span><span class="sxs-lookup"><span data-stu-id="c417d-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="c417d-132">Inserire il codice seguente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c417d-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c417d-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="c417d-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
