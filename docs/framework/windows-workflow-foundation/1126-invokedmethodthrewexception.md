---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 714a98a300426d80c3b494d701ae1bd53a49592f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512294"
---
# <a name="1126---invokedmethodthrewexception"></a>1126 - InvokedMethodThrewException
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|1126|  
|Parole chiave|WFRuntime|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che è stata generata un'eccezione dal metodo chiamato dall'attività InvokeMethod.  
  
## <a name="message"></a>Messaggio  
 È stata generata un'eccezione nel metodo chiamato dall'attività '%1'. %2  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Nome visualizzato dell'attività InvokeMethod.|  
|Eccezione|xs:string|Dettagli dell'eccezione.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
