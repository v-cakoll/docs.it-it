---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Esegue il mapping di un servizio a un endpoint.  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceToEndpointAssociation non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceToEndpointAssociation dispone delle proprietà seguenti:  
  
### <a name="ref"></a>ref  
 Tipo di dati: servizio  
  
 Tipo di accesso: sola lettura  
Qualificatori: chiave  
  
 Servizio associato all'endpoint.  
  
### <a name="ref"></a>ref  
 Tipo di dati: endpoint  
  
 Tipo di accesso: sola lettura  
Qualificatori: chiave  
  
 Endpoint associato al servizio.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
