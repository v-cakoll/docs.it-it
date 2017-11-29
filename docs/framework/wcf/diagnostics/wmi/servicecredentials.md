---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Impostazioni di provisioning e autenticazione dei certificati client per il servizio.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni correnti di autenticazione del token rilasciato per il servizio.  
  
### <a name="peer"></a>Peer  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni correnti di provisioning e autenticazione delle credenziali utilizzate dagli endpoint di trasporto del peer.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Specifica le impostazioni correnti per le conversazioni protette.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Certificato associato al servizio.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni di nome utente e password per il servizio.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni di autenticazione Windows per il servizio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ServiceCredentials>
