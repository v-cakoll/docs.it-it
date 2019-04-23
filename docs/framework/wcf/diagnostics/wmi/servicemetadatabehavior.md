---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976137"
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceMetadataBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceMetadataBehavior dispone delle proprietà seguenti:  
  
### <a name="externalmetadatalocation"></a>ExternalMetadataLocation  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Imposta il percorso a cui il servizio reindirizza richieste di metadati.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL all'indirizzo controllato dall'attributo `HttpGetUrl`.  
  
### <a name="httpgeturl"></a>HttpGetUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTP.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Definisce se il servizio pubblica il relativo WSDL su HTTPS all'indirizzo controllato dall'attributo `HttpsGetUrl`.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Imposta il percorso in cui è pubblicato il WSDL del servizio per il recupero tramite HTTPS.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
