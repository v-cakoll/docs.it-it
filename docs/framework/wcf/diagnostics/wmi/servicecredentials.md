---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 18100ac36b5116c2373171ff795fc23b75bbd6f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572120"
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceCredentials non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceCredentials dispone delle proprietà seguenti:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni di provisioning e autenticazione dei certificati client per il servizio.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni correnti di autenticazione del token rilasciato per il servizio.  
  
### <a name="peer"></a>Peer  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Specifica le impostazioni correnti per le conversazioni protette.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Certificato associato al servizio.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni di nome utente e password per il servizio.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni di autenticazione Windows per il servizio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Description.ServiceCredentials>
