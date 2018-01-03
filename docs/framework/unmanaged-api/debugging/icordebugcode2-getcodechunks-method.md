---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCodeChunks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b90913f05cc2e0a3e98a5890f76a41eb2eafc6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `cbufSize`  
 [in] Dimensioni di `chunks` matrice.  
  
 `pcnumChunks`  
 [out] Il numero di blocchi restituiti nella `chunks` matrice.  
  
 `chunks`  
 [out] Matrice di strutture "CodeChunkInfo", ognuno dei quali rappresenta un singolo blocco di codice. Se il valore di `cbufSize` è 0, questo parametro può essere null.  
  
## <a name="remarks"></a>Note  
 I blocchi di codice si sovrapporranno mai e seguiranno l'ordine in cui sarebbero stati concatenati da [ICorDebugCode:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md). Un oggetto di codice Microsoft intermediate language (MSIL) in .NET Framework versione 2.0 includerà un solo blocco di codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
