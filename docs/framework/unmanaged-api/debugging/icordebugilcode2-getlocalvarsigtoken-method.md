---
title: Metodo ICorDebugILCode2::GetLocalVarSigToken
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
ms.openlocfilehash: 3b9c2f0e20488826aca202b3ef454104964b8bb9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210345"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>Metodo ICorDebugILCode2::GetLocalVarSigToken
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Ottiene il token di metadati per la firma di una variabile locale della funzione rappresentata da questa istanza.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pmdSig`  
 [out] Puntatore al token `mdSignature` per la firma di una variabile locale di questa funzione o `mdSignatureNil` se non è presenta alcuna firma, ovvero se la funzione non contiene variabili locali.  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
