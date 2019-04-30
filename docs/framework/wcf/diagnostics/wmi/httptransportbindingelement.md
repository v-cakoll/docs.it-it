---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 5e23342d57621554aaec67c5c568bb75202a9454
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963488"
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement
HttpTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe HttpTransportBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe HttpTransportBindingElement dispone delle proprietà seguenti:  
  
### <a name="allowcookies"></a>AllowCookies  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se il client accetta cookie e li propaga alle richieste future.  
  
### <a name="authenticationscheme"></a>AuthenticationScheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Schema di autenticazione utilizzato per autenticare le richieste del client da elaborare mediante un listener HTTP.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se i proxy vengono ignorati per gli indirizzi locali.  
  
### <a name="hostnamecomparisonmode"></a>HostnameComparisonMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se viene usato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Se attivato, le connessioni HTTP vengono mantenute attive indipendentemente dal livello di attività.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Dimensione massima del pool di buffer.  
  
### <a name="proxyaddress"></a>ProxyAddress  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 URI contenente l'indirizzo del proxy da utilizzare per le richieste HTTP.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Schema di autenticazione utilizzato per autenticare le richieste del client da elaborare mediante un listener HTTP.  
  
### <a name="realm"></a>Realm  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Area di autenticazione.  
  
### <a name="transfermode"></a>TransferMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Valore che specifica se i messaggi vengono memorizzati nel buffer o trasmessi in caso di richiesta o risposta.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se sul server è attivata la condivisione di connessioni non sicure.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se vengono utilizzate impostazioni proxy a livello di computer invece delle specifiche impostazioni utente.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
