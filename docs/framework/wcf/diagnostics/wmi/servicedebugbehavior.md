---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 76c4992c5364ed9800e58d120c099aceedb2799c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceDebugBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceDebugBehavior dispone delle proprietà seguenti:  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
