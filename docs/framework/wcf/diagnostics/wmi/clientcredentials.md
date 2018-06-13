---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: aa852ff82c44a3b5009dbc70e1067face44cbbe9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486376"
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ClientCredentials non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ClientCredentials dispone delle proprietà seguenti:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Certificato X.509 utilizzato dal client per l'autenticazione per il servizio.  
  
### <a name="httpdigest"></a>HttpDigest  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Credenziale digest HTTP corrente.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Indirizzo e associazione dell'endpoint utilizzati per contattare il servizio locale del token di sicurezza.  
  
### <a name="peer"></a>Peer  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Credenziali utilizzate dal nodo peer per l'autenticazione con gli altri nodi nella rete.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Certificato X.509 del servizio.  
  
### <a name="supportinteractive"></a>SupportInteractive  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se la credenziale supporta negoziazioni interattive.  
  
### <a name="username"></a>UserName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome utente e password utilizzati dal client per l'autenticazione per il servizio.  
  
### <a name="windows"></a>WINDOWS  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Credenziali Windows utilizzate dal client per l'autenticazione per il servizio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ClientCredentials>
