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
ms.openlocfilehash: b9185600d9d8b2a33830d86642727ac54b87a9cf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099649"
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Questo runtime include un evento debugger gestito non di recupero da inviare. Vedere la sezione Osservazioni per la distinzione tra eventi di recupero e non di recupero.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|L'evento gestito in sospeso è una richiesta <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.|  
  
## <a name="remarks"></a>Note  
 Gli eventi di aggiornamento includono le notifiche relative a processo, dominio applicazione, assembly, modulo e creazione thread che consentono al debugger di raggiungere lo stato corrente dopo che è stato collegato a un processo. Gli eventi non di recupero, indicati dal flag `CLR_DEBUGGING_MANAGED_EVENT_PENDING`, includono tutti gli altri eventi del debugger, ad esempio le eccezioni e le notifiche dell'assistente al debug gestito (MDA).  
  
 Il flag `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` consente al runtime di distinguere tra un'eccezione di terminazione e una richiesta di associazione di un debugger gestito che può essere annullato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. idl, Metahost. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
