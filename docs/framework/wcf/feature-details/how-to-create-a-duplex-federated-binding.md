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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedura: creare un'associazione federata duplex

<xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply. Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata. Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP. Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.

È inoltre possibile creare l'associazione nel codice. Per una descrizione dello stack di elementi di associazione da creare, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Per creare un'associazione personalizzata federata duplex con HTTP

1. Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexHttpMessageSecurityBinding`.

3. All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.

4. All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vuoto.

6. Dopo l' [\<elemento > CompositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , creare un elemento [\<oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vuoto.

7. Dopo l' [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, creare un elemento [\<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP

1. Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexTcpMessageSecurityBinding`.

3. All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.

4. All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP

1. Nel [\<binding >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un elemento [\<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. All'interno dell'elemento [\<custombinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) creare un elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) con l'attributo `name` impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.

3. All'interno dell'elemento [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) creare un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo `authenticationMode` impostato su `SecureConversation`.

4. All'interno dell'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un elemento [\<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo `authenticationMode` impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Dopo l'elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [\<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vuoto.

6. Dopo l' [\<elemento > sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , creare un elemento [\<> TcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.

## <a name="code-sample"></a>Esempio di codice

### <a name="sample-with-3-bindings"></a>Esempio con 3 associazioni

1. Inserire il codice seguente nel file di configurazione.

## <a name="example"></a>Esempio

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
