---
title: Metodo ICorDebugMDA::GetXML
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 874462e37aa10af589f39ed099de899ff7155d24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmdagetxml-method"></a>Metodo ICorDebugMDA::GetXML
Ottiene il flusso XML completo associato assistente al debug gestito (MDA) rappresentato da [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchName`  
 [in] Dimensione della matrice `szName`.  
  
 `pcchName`  
 [out] Puntatore alla lunghezza del flusso XML.  
  
 `szName`  
 [out] Matrice in cui archiviare il flusso XML. La matrice può essere vuota.  
  
## <a name="remarks"></a>Note  
 Il `GetXML` metodo potrebbe influire sulle prestazioni, a seconda delle dimensioni del flusso XML associato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
