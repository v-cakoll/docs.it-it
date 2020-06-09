---
title: "Procedura: creare un'associazione federata duplex"
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: e93651ce9fe9dae55c299fcb061da6bdc4b6bc5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598970"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="64d90-102">Procedura: creare un'associazione federata duplex</span><span class="sxs-lookup"><span data-stu-id="64d90-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="64d90-103"><xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply.</span><span class="sxs-lookup"><span data-stu-id="64d90-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="64d90-104">Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="64d90-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="64d90-105">Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="64d90-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="64d90-106">Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.</span><span class="sxs-lookup"><span data-stu-id="64d90-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="64d90-107">È inoltre possibile creare l'associazione nel codice.</span><span class="sxs-lookup"><span data-stu-id="64d90-107">You can also create the binding in code.</span></span> <span data-ttu-id="64d90-108">Per una descrizione dello stack di elementi di associazione da creare, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="64d90-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="64d90-109">Per creare un'associazione personalizzata federata duplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="64d90-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="64d90-110">Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="64d90-110">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="64d90-111">All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexHttpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="64d90-111">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="64d90-112">All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="64d90-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="64d90-113">All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="64d90-113">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="64d90-114">Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-114">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="64d90-115">Dopo l' [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento, creare un [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-115">Following the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="64d90-116">Dopo l' [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento, creare un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-116">Following the [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="64d90-117">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP</span><span class="sxs-lookup"><span data-stu-id="64d90-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="64d90-118">Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="64d90-118">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="64d90-119">All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexTcpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="64d90-119">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="64d90-120">All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="64d90-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="64d90-121">All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="64d90-121">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="64d90-122">Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-122">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="64d90-123">Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP</span><span class="sxs-lookup"><span data-stu-id="64d90-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="64d90-124">Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="64d90-124">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="64d90-125">All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .</span><span class="sxs-lookup"><span data-stu-id="64d90-125">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="64d90-126">All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="64d90-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="64d90-127">All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="64d90-127">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="64d90-128">Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-128">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="64d90-129">Dopo l' [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, creare un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="64d90-129">Following the [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="64d90-130">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="64d90-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="64d90-131">Esempio con 3 associazioni</span><span class="sxs-lookup"><span data-stu-id="64d90-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="64d90-132">Inserire il codice seguente nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="64d90-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="64d90-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="64d90-133">Example</span></span>

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
