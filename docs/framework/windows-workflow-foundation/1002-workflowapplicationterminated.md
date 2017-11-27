---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a>1002 - WorkflowApplicationTerminated
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1002|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'applicazione flusso di lavoro è terminata nello stato Faulted con un'eccezione.  
  
## <a name="message"></a>Messaggio  
 WorkflowApplication con ID: '%1' terminata. È stata completata nello stato Faulted con un'eccezione.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|ID applicazione flusso di lavoro|  
|Eccezione|`xs:string`|Dettagli dell'eccezione.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
