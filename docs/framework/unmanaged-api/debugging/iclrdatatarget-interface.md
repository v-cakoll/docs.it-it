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
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793711"
---
# <a name="iclrdatatarget-interface"></a>Interfaccia ICLRDataTarget
Fornisce metodi per l'interazione con un elemento di destinazione del Common Language Runtime (CLR).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCurrentThreadID](iclrdatatarget-getcurrentthreadid-method.md)|Ottiene l'identificatore del sistema operativo per il thread corrente.|  
|[Metodo GetImageBase](iclrdatatarget-getimagebase-method.md)|Ottiene l'indirizzo di memoria di base per l'immagine specificata.|  
|[Metodo GetMachineType](iclrdatatarget-getmachinetype-method.md)|Ottiene un identificatore per il tipo di set di istruzioni utilizzato dal processo di destinazione.|  
|[Metodo GetPointerSize](iclrdatatarget-getpointersize-method.md)|Ottiene la dimensione, in byte, di un puntatore alla destinazione corrente.|  
|[Metodo GetThreadContext](iclrdatatarget-getthreadcontext-method.md)|Ottiene un puntatore al contesto del thread con l'identificatore specificato.|  
|[Metodo GetTLSValue](iclrdatatarget-gettlsvalue-method.md)|Ottiene un valore nella risorsa di archiviazione thread-local (TLS) in corrispondenza dell'indice specificato per il thread specificato.|  
|[Metodo ReadVirtual](iclrdatatarget-readvirtual-method.md)|Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.|  
|[Metodo Request](iclrdatatarget-request-method.md)|Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per richiedere un'operazione, come definito dall'implementazione di.|  
|[Metodo SetThreadContext](iclrdatatarget-setthreadcontext-method.md)|Imposta il contesto corrente del thread specificato nel processo di destinazione.|  
|[Metodo SetTLSValue](iclrdatatarget-settlsvalue-method.md)|Imposta un valore nell'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.|  
|[Metodo WriteVirtual](iclrdatatarget-writevirtual-method.md)|Scrive i dati dal buffer specificato nell'indirizzo di memoria virtuale specificato.|  
  
## <a name="remarks"></a>Note  
 Il client API (ovvero il debugger) deve implementare questa interfaccia in modo appropriato per l'elemento di destinazione specifico. L'implementazione per un processo reale, ad esempio, è diversa da quella di un dump di memoria.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
