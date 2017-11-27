---
title: Metodo ICorDebugSymbolProvider2::GetFrameProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3892b8da3286132709792513f055d6ce75bd3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a>Metodo ICorDebugSymbolProvider2::GetFrameProps
Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `codeRva`  
 [in] Indirizzo RVA (Relative Virtual Address)  
  
 `pCodeStartRva`  
 [out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del metodo.  
  
 `pParentFrameStartRva`  
 [out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del frame.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
