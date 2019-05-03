---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032266"
---
# <a name="1015---startcompletionworkitem"></a>1015 - StartCompletionWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1015|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che viene avviata l'esecuzione di CompletionWorkItem.  
  
## <a name="message"></a>Messaggio  
 Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'. Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Nome tipo dell'attività padre.|  
|ParentDisplayName|xs:string|Nome visualizzato dell'attività padre.|  
|ParentInstanceId|xs:string|ID dell'istanza dell'attività padre.|  
|CompletedActivity|xs:string|Nome tipo dell'attività completata.|  
|CompletedActivityDisplayName|xs:string|Nome visualizzato dell'attività completata.|  
|CompletedActivityInstanceId|xs:string|L'ID dell'istanza dell'attività completata.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
