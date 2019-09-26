---
title: Enumerazione CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274107"
---
# <a name="clr_debugging_process_flags-enumeration"></a>Enumerazione CLR_DEBUGGING_PROCESS_FLAGS
Fornisce i valori utilizzati dal metodo [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Questo runtime include un evento debugger gestito non di recupero da inviare. Vedere la sezione Osservazioni per la distinzione tra eventi di recupero e non di recupero.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|L'evento gestito in sospeso è una <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> richiesta.|  
  
## <a name="remarks"></a>Note  
 Gli eventi di aggiornamento includono le notifiche relative a processo, dominio applicazione, assembly, modulo e creazione thread che consentono al debugger di raggiungere lo stato corrente dopo che è stato collegato a un processo. Gli eventi non di recupero, indicati dal `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, includono tutti gli altri eventi del debugger, ad esempio le eccezioni e le notifiche dell'assistente al debug gestito (MDA).  
  
 Il `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag consente al runtime di distinguere tra un'eccezione di terminazione e una richiesta di associazione di un debugger gestito che può essere annullato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. idl, Metahost. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
