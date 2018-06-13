---
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 198e11dd94b0ad5cdc1e01c3611280754ca081d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510034"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1035|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che un'attività ha impostato la transazione runtime.  
  
## <a name="message"></a>Messaggio  
 La transazione di runtime è stata impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'.  Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|IsolatedActivity|xs:string|Il nome del tipo di attività che la transazione su cui è isolata.|  
|IsolatedActivityDisplayName|xs:string|Il nome visualizzato dell'attività che la transazione su cui è isolata.|  
|IsolatedActivityInstanceId|xs:string|L'ID istanza dell'attività che la transazione su cui è isolata.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
