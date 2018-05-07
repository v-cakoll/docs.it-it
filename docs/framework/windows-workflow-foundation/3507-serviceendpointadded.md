---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="3507---serviceendpointadded"></a>3507 - ServiceEndpointAdded
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3507|  
|Parole chiave|WFServices|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che un endpoint del servizio è stato aggiunto.  
  
## <a name="message"></a>Messaggio  
 È stato aggiunto un endpoint del servizio per l'indirizzo '%1', binding '%2' e contratto '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Address|xs:string|L'indirizzo dell'endpoint.|  
|Binding|xs:string|L'associazione dell'endpoint.|  
|Contratto|xs:string|Il contratto dell'endpoint.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
