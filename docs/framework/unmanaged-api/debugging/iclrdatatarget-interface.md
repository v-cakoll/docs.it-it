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
ms.openlocfilehash: b0a5abe8877c8414443fadc00e223df240721132
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget-interface"></a>Interfaccia ICLRDataTarget
Fornisce metodi per l'interazione con un elemento di destinazione di common language runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCurrentThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Ottiene l'identificatore del sistema operativo per il thread corrente.|  
|[Metodo GetImageBase](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Ottiene l'indirizzo di memoria di base per l'immagine specificata.|  
|[Metodo GetMachineType](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Ottiene un identificatore per il tipo di set di istruzioni che utilizza il processo di destinazione.|  
|[Metodo GetPointerSize](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Ottiene le dimensioni, in byte, di un puntatore alla destinazione corrente.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Ottiene un puntatore al contesto del thread, con l'identificatore specificato.|  
|[Metodo GetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Ottiene un valore nella memoria locale di thread (TLS) in corrispondenza dell'indice specificato per il thread specificato.|  
|[Metodo ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.|  
|[Metodo Request](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per richiedere un'operazione, come definito dall'implementazione.|  
|[Metodo SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Imposta il contesto corrente del thread specificato nel processo di destinazione.|  
|[Metodo SetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Imposta un valore nell'archiviazione locale di thread (TLS) del thread nel processo di destinazione specificato.|  
|[Metodo WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Scrive dati dal buffer specificato per l'indirizzo di memoria virtuale specificato.|  
  
## <a name="remarks"></a>Note  
 Il client di API (ovvero, il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico. L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
