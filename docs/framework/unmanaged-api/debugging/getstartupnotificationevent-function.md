---
title: Funzione GetStartupNotificationEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetStartupNotificationEvent
api_location: dbgshim.dll
api_type: COM
f1_keywords: GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 809f34d265e0a1677d8b7fc78515b20df7353968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getstartupnotificationevent-function"></a>Funzione GetStartupNotificationEvent
Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
#### <a name="parameters"></a>Parametri  
 `debuggeePID`  
 [in] Identificatore del processo di destinazione da cui ricevere le notifiche di avvio CLR.  
  
 `phStartupEvent`  
 [out] Puntatore a un handle che verrà segnalato da CLR all'avvio.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 L'handle all'evento di notifica di avvio è stato ottenuto correttamente.  
  
 E_INVALIDARG  
 `phStartupEvent` è null o `debuggeePID` non fa riferimento a un processo attualmente in esecuzione.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Non è possibile ottenere l'handle all'evento di notifica di avvio.  
  
## <a name="remarks"></a>Note  
 Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.  
  
 L'evento viene segnalato prima che qualsiasi codice gestito venga eseguito dal CLR che ha segnalato l'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim.dll  
  
 **Versioni di .NET framework:** 3.5 SP1
