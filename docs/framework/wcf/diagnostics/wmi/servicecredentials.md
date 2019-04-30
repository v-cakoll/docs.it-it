---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956980"
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
