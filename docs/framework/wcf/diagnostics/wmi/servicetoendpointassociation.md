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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f576c2f82590f683aa51d5cc70c67a4a2b15a1e0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
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
