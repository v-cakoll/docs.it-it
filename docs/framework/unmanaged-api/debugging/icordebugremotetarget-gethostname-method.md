---
title: Metodo ICorDebugRemoteTarget::GetHostName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget.GetHostName
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45fa4afebda00cb2549a5c18ba81c6bb4e8210e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetargetgethostname-method"></a>Metodo ICorDebugRemoteTarget::GetHostName
Restituisce il nome di dominio completo o l'indirizzo IPv4 del computer di destinazione per il debug remoto. IPV6 non è attualmente supportato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchHostName`  
 [in] La dimensione, in caratteri, del `szHostName` buffer. Se il parametro è 0 (zero), `szHostName` deve essere Null.  
  
 `pcchHostName`  
 [out] Numero di caratteri, incluso un terminatore Null, nel nome host o nell'indirizzo IP. Questo parametro può essere null.  
  
 `szHostName`  
 [out] Buffer contenente il nome host o l'indirizzo IP.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il nome host o l'indirizzo IP è stato restituito correttamente.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile restituire il nome host o l'indirizzo IP.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene implementato dal writer del debugger. Deve attenersi al paradigma di chiamate multiple: alla prima chiamata, il chiamante passa Null sia a `cchHostName` sia a `szHostName` e tramite `pcchHostName` viene restituita la dimensione del buffer richiesto. Nella seconda chiamata, la dimensione che è stata restituita in precedenza viene passata a `cchHostName` e un buffer di dimensioni appropriate viene passato a `szHostName`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
