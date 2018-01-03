---
title: Metodo ICorDebugProcess7::SetWriteableMetadataUpdateMode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e901fd623893b9c03e1b5835adc72c6bd225ead4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>Metodo ICorDebugProcess7::SetWriteableMetadataUpdateMode
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Configura come il debugger gestisce gli aggiornamenti in memoria ai metadati all'interno del processo di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `flags`  
 Oggetto [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) valore di enumerazione che specifica se gli aggiornamenti in memoria ai metadati nel processo di destinazione sono visibili (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) o non visibili (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) al debugger.  
  
## <a name="remarks"></a>Note  
 Gli aggiornamenti ai metadati del processo di destinazione possono provenire dalle opzioni di Modifica e continuazione, da un profiler o da <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugProcess7](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
