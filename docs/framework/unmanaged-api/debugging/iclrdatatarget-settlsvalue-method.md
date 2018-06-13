---
title: Metodo ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18733c2d643a75f9bb11159ba4acdbc8ab064c55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404110"
---
# <a name="iclrdatatargetsettlsvalue-method"></a>Metodo ICLRDataTarget::SetTLSValue
Imposta un valore nell'archiviazione locale di thread (TLS) del thread nel processo di destinazione specificato. Questo metodo viene chiamato da servizi di accesso dati di common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [in] Identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `index`  
 [in] Indice della posizione. Questo valore deve essere un indice valido nell'archivio locale del thread specificato.  
  
 `value`  
 [in] Oggetto `CLRDATA_ADDRESS` valore che specifica il valore da inserire nel percorso TLS specificato.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
