---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1131|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Durante il passaggio CacheMetadata, l'attività InvokeMethod indica che viene usato il modello asincrono quando viene richiamato il metodo.  
  
## <a name="message"></a>Messaggio  
 InvokeMethod '%1': il metodo usa un modello asincrono di '%2' e '%3'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Nome visualizzato dell'attività InvokeMethod.|  
|BeginMethod|xs:string|Nome del metodo Begin.|  
|EndMethod|xs:string|Nome del metodo End.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
