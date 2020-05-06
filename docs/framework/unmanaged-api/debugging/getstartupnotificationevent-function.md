---
title: Funzione GetStartupNotificationEvent
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 3377dcd5d45ca8e31a57a75bd81366d41837c12c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860705"
---
# <a name="getstartupnotificationevent-function"></a>Funzione GetStartupNotificationEvent
Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a>Parametri  
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
  
## <a name="remarks"></a>Osservazioni  
 Nel sistema operativo Windows `debuggeePID` esegue il mapping a un identificatore di processo del sistema operativo.  
  
 L'evento viene segnalato prima che qualsiasi codice gestito venga eseguito dal CLR che ha segnalato l'evento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** dbgshim. h  
  
 **Libreria:** dbgshim. dll  
  
 **Versioni .NET Framework:** 3,5 SP1
