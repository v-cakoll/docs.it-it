---
title: "Procedura: Creare un'associazione federata duplex"
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972064"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="44f70-102">Procedura: Creare un'associazione federata duplex</span><span class="sxs-lookup"><span data-stu-id="44f70-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="44f70-103"><xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply.</span><span class="sxs-lookup"><span data-stu-id="44f70-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="44f70-104">Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="44f70-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="44f70-105">Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="44f70-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="44f70-106">Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.</span><span class="sxs-lookup"><span data-stu-id="44f70-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="44f70-107">È inoltre possibile creare l'associazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="44f70-107">You can also create the binding in code.</span></span> <span data-ttu-id="44f70-108">Per una descrizione dello stack di elementi di associazione da creare, [vedere Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="44f70-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="44f70-109">Per creare un'associazione personalizzata federata duplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="44f70-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="44f70-110">Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="44f70-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="44f70-111">All' `name` interno dell' `FederationDuplexHttpMessageSecurityBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="44f70-112">All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="44f70-113">All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.</span><span class="sxs-lookup"><span data-stu-id="44f70-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="44f70-114">Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="44f70-115">Dopo l' [ \<elemento > CompositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , creare un elemento [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="44f70-116">In seguito all' [ \<elemento > oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , creare un elemento [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="44f70-117">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP</span><span class="sxs-lookup"><span data-stu-id="44f70-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="44f70-118">Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="44f70-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="44f70-119">All' `name` interno dell' `FederationDuplexTcpMessageSecurityBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="44f70-120">All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="44f70-121">All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.</span><span class="sxs-lookup"><span data-stu-id="44f70-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="44f70-122">Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="44f70-123">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP</span><span class="sxs-lookup"><span data-stu-id="44f70-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="44f70-124">Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="44f70-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="44f70-125">All' `name` interno dell' `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="44f70-126">All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.</span><span class="sxs-lookup"><span data-stu-id="44f70-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="44f70-127">All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.</span><span class="sxs-lookup"><span data-stu-id="44f70-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="44f70-128">Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="44f70-129">Dopo l' [ \<elemento > sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , creare un elemento [ \<> TcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.</span><span class="sxs-lookup"><span data-stu-id="44f70-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="44f70-130">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="44f70-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="44f70-131">Esempio con 3 associazioni</span><span class="sxs-lookup"><span data-stu-id="44f70-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="44f70-132">Inserire il codice seguente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="44f70-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="44f70-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="44f70-133">Example</span></span>

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
