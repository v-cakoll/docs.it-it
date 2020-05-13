---
title: Metodo ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: 020724c422af7cba0165e6f37d0eacb7742153ec
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379265"
---
# <a name="icordebugremotetargetgethostname-method"></a>Metodo ICorDebugRemoteTarget::GetHostName
Restituisce il nome di dominio completo o l'indirizzo IPv4 del computer di destinazione per il debug remoto. IPV6 non è attualmente supportato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Parametri  
 `cchHostName`  
 in Dimensione, in caratteri, del `szHostName` buffer. Se il parametro è 0 (zero), `szHostName` deve essere Null.  
  
 `pcchHostName`  
 [out] Numero di caratteri, incluso un terminatore Null, nel nome host o nell'indirizzo IP. Questo parametro può essere null.  
  
 `szHostName`  
 [out] Buffer contenente il nome host o l'indirizzo IP.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il nome host o l'indirizzo IP è stato restituito correttamente.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile restituire il nome host o l'indirizzo IP.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo viene implementato dal writer del debugger. Deve seguire il paradigma di chiamata multipla: alla prima chiamata, il chiamante passa null sia a `cchHostName` che a e `szHostName` `pcchHostName` restituisce la dimensione del buffer richiesto. Nella seconda chiamata, la dimensione che è stata restituita in precedenza viene passata a `cchHostName` e un buffer di dimensioni appropriate viene passato a `szHostName`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Interfaccia ICorDebug](icordebug-interface.md)
