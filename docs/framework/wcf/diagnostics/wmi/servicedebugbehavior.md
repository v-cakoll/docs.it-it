---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768657"
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
  
 Tipo di accesso: Sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se includere informazioni di eccezione nei dettagli degli errori SOAP restituiti ai client a fini di debug.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
