---
title: Enumerazione ESymbolReadingPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ESymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ESymbolReadingPolicy
helpviewer_keywords: ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ce56486453e88a18ebd9dbb42f30bcfdafcf328e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a>Enumerazione ESymbolReadingPolicy
Contiene valori che impostano i criteri per la lettura dei file di programma (PDB) di database.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Specifica che il debugger deve sempre leggere i file PDB.|  
|`eSymbolReadingFullTrustOnly`|Specifica che il debugger deve leggere solo i file PDB sono associati gli assembly con attendibilità.|  
|`eSymbolReadingNever`|Specifica che il debugger non deve leggere i file PDB.|  
  
## <a name="remarks"></a>Note  
 Il `ESymbolReadingPolicy` enumerazione viene utilizzata con la [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
