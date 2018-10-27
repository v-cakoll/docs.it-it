---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 8b6200f84f352d49cf142d9c8b97d1c2b36149b2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180900"
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
