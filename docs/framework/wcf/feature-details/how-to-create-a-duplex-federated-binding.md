---
title: "Procedura: creare un'associazione federata duplex"
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141725"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="6e85b-102">Procedura: creare un'associazione federata duplex</span><span class="sxs-lookup"><span data-stu-id="6e85b-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="6e85b-103"><xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply.</span><span class="sxs-lookup"><span data-stu-id="6e85b-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="6e85b-104">Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="6e85b-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="6e85b-105">Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="6e85b-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="6e85b-106">Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.</span><span class="sxs-lookup"><span data-stu-id="6e85b-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="6e85b-107">È inoltre possibile creare l'associazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="6e85b-107">You can also create the binding in code.</span></span> <span data-ttu-id="6e85b-108">Per una descrizione dello stack di elementi di associazione da creare, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="6e85b-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="6e85b-109">Per creare un'associazione personalizzata federata duplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="6e85b-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="6e85b-110">Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e85b-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="6e85b-111">All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="6e85b-112">All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="6e85b-113">All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="6e85b-114">Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="6e85b-115">Dopo l' [\<elemento > CompositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , creare un elemento [\<oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="6e85b-116">Dopo l' [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, creare un elemento [\<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="6e85b-117">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP</span><span class="sxs-lookup"><span data-stu-id="6e85b-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="6e85b-118">Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e85b-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="6e85b-119">All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="6e85b-120">All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="6e85b-121">All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="6e85b-122">Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="6e85b-123">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP</span><span class="sxs-lookup"><span data-stu-id="6e85b-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="6e85b-124">Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6e85b-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="6e85b-125">All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="6e85b-126">All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="6e85b-127">All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="6e85b-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="6e85b-128">Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="6e85b-129">Dopo l' [\<elemento > sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , creare un elemento [\<> TcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="6e85b-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="6e85b-130">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="6e85b-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="6e85b-131">Esempio con 3 associazioni</span><span class="sxs-lookup"><span data-stu-id="6e85b-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="6e85b-132">Inserire il codice seguente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e85b-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="6e85b-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e85b-133">Example</span></span>

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
