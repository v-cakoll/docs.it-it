---
title: ServiceToEndpointAssociation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d2755294ba02b4d67bd7f62cf020a44525874d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
