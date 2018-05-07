---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d0758a8603b7c31844b39c9f3beefea04e0a029
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Metodo ICorDebugProcess6::GetExportStepInfo
Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a>Parametri  
 pszExportName  
 [in] Il nome di una funzione di runtime di esportazione così come è scritta nella tabella di esportazione PE.  
  
 invokeKind  
 [out] Un puntatore a un membro del [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumerazione che descrive come la funzione esportata richiama il codice gestito.  
  
 invokePurpose  
 [out] Un puntatore a un membro del [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumerazione che descrive perché la funzione esportata chiama il codice gestito.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo può restituire i valori elencati nella seguente tabella.  
  
|Valore restituito|Descrizione|  
|------------------|-----------------|  
|`S_OK`|La chiamata al metodo è stata completata correttamente.|  
|`E_POINTER`|`pInvokeKind` o `pInvokePurpose` viene **null**.|  
|Altri valori di `HRESULT` con errori.|A seconda dei casi.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
