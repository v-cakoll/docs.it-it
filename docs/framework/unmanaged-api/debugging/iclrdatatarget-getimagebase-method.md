---
title: Metodo ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: fed643ae52f50b1b8cd134880c644c8941da6f56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122871"
---
# <a name="iclrdatatargetgetimagebase-method"></a>Metodo ICLRDataTarget::GetImageBase
Ottiene l'indirizzo di memoria di base dell'immagine specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `imagePath`  
 in Nome file dell'immagine, incluso il percorso.  
  
 `baseAddress`  
 out Puntatore a un CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.  
  
## <a name="remarks"></a>Note  
 Il nome del file di immagine non può contenere un percorso. Se viene specificato un percorso, la corrispondenza viene eseguita sull'intero percorso. in caso contrario, la corrispondenza viene eseguita solo sul nome del file.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
