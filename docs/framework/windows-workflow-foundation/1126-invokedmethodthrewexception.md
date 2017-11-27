---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b11c2f167ce7afce992cddb2f32f840212d4ac8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
