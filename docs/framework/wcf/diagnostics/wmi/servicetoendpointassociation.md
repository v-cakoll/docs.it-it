---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372187"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
Esegue il mapping di un servizio a un endpoint.  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
