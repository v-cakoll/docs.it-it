---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 68b2350f257bc95d8e17f4b9049d67c7f67becae
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452862"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
