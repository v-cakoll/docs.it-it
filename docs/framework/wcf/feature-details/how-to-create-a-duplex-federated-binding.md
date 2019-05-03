---
title: "Procedura: Creare un'associazione federata duplex"
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696210"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedura: Creare un'associazione federata duplex
<xref:System.ServiceModel.WSFederationHttpBinding> supporta solo contratti di scambio di datagrammi e messaggi request/reply. Per utilizzare il contratto di scambio di messaggi duplex, è necessario creare un'associazione personalizzata. Nelle procedure seguenti viene illustrato come effettuare questa operazione nella configurazione, utilizzando la sicurezza in modalità messaggio per i trasporti HTTP e TCP e la sicurezza in modalità mista per il trasporto TCP. Alla fine di questo argomento viene riportato il codice di esempio che illustra tutte e 3 le associazioni.  
  
 È inoltre possibile creare l'associazione nel codice. Per una descrizione dello stack di elementi di associazione per creare, vedere [come: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Per creare un'associazione personalizzata federata duplex con HTTP  
  
1. Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.  
  
2. All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexHttpMessageSecurityBinding`.  
  
3. All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.  
  
4. All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.  
  
5. Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento.  
  
6. Seguendo la [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento, creare un oggetto vuoto [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento.  
  
7. Seguendo la [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, creare un oggetto vuoto [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) elemento.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza dei messaggi TCP  
  
1. Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.   
  
2. All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexTcpMessageSecurityBinding`.  
  
3. All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.  
  
4. All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.  
  
5. Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Per creare un'associazione personalizzata federata duplex con la modalità di sicurezza mista TCP  
  
1. Nel [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del file di configurazione, creare un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.   
  
2. All'interno di [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, creare un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento con la `name` attributo impostato su `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.  
  
3. All'interno di [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento, creare un [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` attributo impostato su `SecureConversation`.  
  
4. All'interno di [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con il `authenticationMode` attributo impostato su `IssuedTokenForCertificate` o`IssuedTokenForSslNegotiated`.  
  
5. Seguendo la [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, creare un oggetto vuoto [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento.  
  
6. Seguendo la [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, creare un oggetto vuoto [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.  
  
## <a name="code-sample"></a>Esempio di codice  
  
#### <a name="sample-with-3-bindings"></a>Esempio con 3 associazioni  
  
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
