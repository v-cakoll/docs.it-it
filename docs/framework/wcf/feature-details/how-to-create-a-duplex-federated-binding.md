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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedura: creare un'associazione federata duplex

<xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply. Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata. Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP. Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.

È inoltre possibile creare l'associazione nel codice. Per una descrizione dello stack di elementi di associazione da creare, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Per creare un'associazione personalizzata federata duplex con HTTP

1. Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexHttpMessageSecurityBinding` .

3. All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .

4. All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento vuoto.

6. Dopo l' [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento, creare un [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento vuoto.

7. Dopo l' [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento, creare un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) elemento vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP

1. Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexTcpMessageSecurityBinding` .

3. All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .

4. All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vuoto.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP

1. Nel [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione creare un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. All'interno dell' [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con l' `name` attributo impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .

3. All'interno dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, creare un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con l' `authenticationMode` attributo impostato su `SecureConversation` .

4. All'interno dell' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con l' `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Dopo l' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento vuoto.

6. Dopo l' [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, creare un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vuoto.

## <a name="code-sample"></a>Codice di esempio

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
