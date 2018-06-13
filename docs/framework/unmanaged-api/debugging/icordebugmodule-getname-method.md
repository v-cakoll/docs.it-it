---
title: Metodo ICorDebugModule::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bebee019595143d25e950719ad62d9e10b76a3e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418906"
---
# <a name="icordebugmodulegetname-method"></a>Metodo ICorDebugModule::GetName
Ottiene il nome del file del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cchname`  
 [in] Dimensione della matrice `szName`.  
  
 `pcchName`  
 [in] Puntatore alla lunghezza del nome restituito.  
  
 `szName`  
 [out] Matrice che archivia il nome restituito.  
  
## <a name="remarks"></a>Note  
 Il `GetName` metodo restituisce un HRESULT S_OK se il nome di file del modulo corrisponde al nome sul disco. `GetName` Restituisce un HRESULT di S_FALSE se il nome viene creato, ad esempio per un modulo dinamico o in memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
 
