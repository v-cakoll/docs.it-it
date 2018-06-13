---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509697"
---
# <a name="1010---activitycompleted"></a>1010 - ActivityCompleted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1010|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che l'esecuzione di un'attività è stata completata.  
  
## <a name="message"></a>Messaggio  
 Attività "%1 " DisplayName:, "%2", InstanceId: "%3 " è stata completata in "%4 " stato.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Attività|xs:string|Il nome del tipo di attività.|  
|DisplayName|xs:string|Nome visualizzato dell'attività.|  
|InstanceId|xs:string|L'ID dell'istanza dell'attività.|  
|Stato|xs:string|Stato dell'attività.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
