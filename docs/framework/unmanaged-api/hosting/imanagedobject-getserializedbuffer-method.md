---
title: Metodo IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53e8180fb55336eb05d0737110fd2fe07a4c5894
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441601"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a>Metodo IManagedObject::GetSerializedBuffer
Ottiene la rappresentazione di stringa dell'oggetto gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pBSTR`  
 [out] Puntatore a una stringa che rappresenta l'oggetto serializzato.  
  
## <a name="remarks"></a>Note  
 Il `GetSerializedBuffer` metodo serializza l'oggetto che può essere sottoposto a marshalling al client.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
