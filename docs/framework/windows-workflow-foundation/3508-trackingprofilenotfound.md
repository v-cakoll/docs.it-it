---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 346cb98b1285883a9a85f2c7abb6147f42734395
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3508|  
|Parole chiave|WFServices|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che TrackingProfile non è presente nel file di configurazione o ActivityDefinitionId non corrisponde al profilo.  
  
## <a name="message"></a>Messaggio  
 Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'. TrackingProfile non incluso nel file di configurazione o ActivityDefinitionId non corrisponde.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|Nome del profilo di rilevamento.|  
|ActivityDefinitionId|xs:string|ID di definizione dell'attività.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
