---
title: Interfaccia ICLRDataTarget
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698109"
---
# <a name="iclrdatatarget-interface"></a>Interfaccia ICLRDataTarget
Fornisce metodi per l'interazione con un elemento di destinazione di common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCurrentThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Ottiene l'identificatore del sistema operativo per il thread corrente.|  
|[Metodo GetImageBase](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Ottiene l'indirizzo di base di memoria per l'immagine specificata.|  
|[Metodo GetMachineType](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Ottiene un identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.|  
|[Metodo GetPointerSize](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Ottiene la dimensione, espressa in byte, di un puntatore alla destinazione corrente.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Ottiene un puntatore al contesto del thread con l'identificatore specificato.|  
|[Metodo GetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Ottiene un valore nell'archiviazione thread-local (TLS) in corrispondenza dell'indice specificato per il thread specificato.|  
|[Metodo ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.|  
|[Metodo Request](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.|  
|[Metodo SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Imposta il contesto corrente del thread specificato nel processo di destinazione.|  
|[Metodo SetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Imposta un valore nell'archiviazione thread-local (TLS) del thread nel processo di destinazione specificato.|  
|[Metodo WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Scrive i dati dal buffer specificato per l'indirizzo di memoria virtuale specificato.|  
  
## <a name="remarks"></a>Note  
 Il client per le API (vale a dire, il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico. L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, ClrData.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
