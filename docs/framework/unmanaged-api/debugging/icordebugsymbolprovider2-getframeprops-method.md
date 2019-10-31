---
title: 'Metodo ICorDebugSymbolProvider2:: Gettypeprops'
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: 39bdb93fcb48da6667d982ca2d511ee5e499ae32
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133637"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a>Metodo ICorDebugSymbolProvider2:: Gettypeprops
Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `codeRva`  
 [in] Indirizzo RVA (Relative Virtual Address)  
  
 `pCodeStartRva`  
 [out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del metodo.  
  
 `pParentFrameStartRva`  
 [out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del frame.  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
