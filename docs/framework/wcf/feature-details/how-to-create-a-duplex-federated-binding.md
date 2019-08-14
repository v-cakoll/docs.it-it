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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedura: Creare un'associazione federata duplex

<xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply. Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata. Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP. Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.

È inoltre possibile creare l'associazione nel codice. Per una descrizione dello stack di elementi di associazione da creare, [vedere Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Per creare un'associazione personalizzata federata duplex con HTTP

1. Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. All' `name` interno dell' `FederationDuplexHttpMessageSecurityBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.

3. All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.

4. All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.

5. Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vuoto.

6. Dopo l' [ \<elemento > CompositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , creare un elemento [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vuoto.

7. In seguito all' [ \<elemento > oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , creare un elemento [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP

1. Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. All' `name` interno dell' `FederationDuplexTcpMessageSecurityBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.

3. All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.

4. All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.

5. Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP

1. Nel nodo [> bindingdelfilediconfigurazionecreareunelementoCustomBinding>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. All' `name` interno dell' `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [ \<elemento > CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , creare un [ \<elemento binding >](../../../../docs/framework/misc/binding.md) con l'attributo impostato su.

3. All' `authenticationMode` interno dell' `SecureConversation` [ \<elemento binding >](../../../../docs/framework/misc/binding.md) creare un [ \<elemento > di sicurezza](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con l'attributo impostato su.

4. All'interno `authenticationMode` dell' `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) creare un [ \<elemento > SecureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con l'attributo impostato su o.

5. Dopo l' [ \<elemento Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , creare un elemento [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vuoto.

6. Dopo l' [ \<elemento > sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , creare un elemento [ \<> TcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vuoto.

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
