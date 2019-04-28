---
title: 1007 - WorkflowApplicationPersisted
ms.date: 03/30/2017
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
ms.openlocfilehash: 0b3c290ad06eda6921626c0d7a1c8ec854c30e7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925268"
---
# <a name="1007---workflowapplicationpersisted"></a>1007 - WorkflowApplicationPersisted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1007|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro è persistente.  
  
## <a name="message"></a>Messaggio  
 WorkflowApplication con ID: '%1' persistente.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|ID applicazione flusso di lavoro|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
