---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84ab475ecb538dcf5bd24c750dfe9c993ea5a0ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470900"
---
# <a name="icordebugcode2getcodechunks-method"></a>Metodo ICorDebugCode2::GetCodeChunks
Ottiene i blocchi di codice che è costituito da questo oggetto di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbufSize`  
 [in] Dimensioni del `chunks` matrice.  
  
 `pcnumChunks`  
 [out] Il numero di blocchi restituite nel `chunks` matrice.  
  
 `chunks`  
 [out] Matrice di strutture "CodeChunkInfo", ognuno dei quali rappresenta un singolo blocco di codice. Se il valore di `cbufSize` è 0, questo parametro può essere null.  
  
## <a name="remarks"></a>Note  
 I blocchi di codice mai si sovrapporranno e gli utenti seguano l'ordine in cui sarebbe stato concatenati dai [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md). Un oggetto di codice Microsoft intermediate language (MSIL) in .NET Framework versione 2.0 includerà un solo blocco di codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

