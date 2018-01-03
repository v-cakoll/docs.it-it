---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3c69bbc904f54636e56be6d235d1070b9fecf1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
|`E_POINTER`|`pInvokeKind`o `pInvokePurpose` è **null**.|  
|Altri valori di `HRESULT` con errori.|A seconda dei casi.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
