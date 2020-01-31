---
title: Funzione _EFN_GetManagedObjectFieldInfo
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793766"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a>\_AAPN\_funzione GetManagedObjectFieldInfo
Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `Client`  
 in Puntatore al client di debug.  
  
 `objAddr`  
 in Puntatore A un oggetto gestito.  
  
 szFieldName  
 in Puntatore a un oggetto gestito al nome del campo.  
  
 `pValue`  
 out Valore del campo. Questo parametro può essere null.  
  
 `pOffset`  
 out Offset da `objAddr` al campo. Questo parametro può essere null.  
  
## <a name="remarks"></a>Note  
 Se l'offset è 0, non viene scritto alcun offset.  
  
 Se nel thread non è attualmente presente codice gestito, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore della funzione messaggi 0XA0 e un codice di errore 0x1000.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** SOS_Stacktrace. h  
  
 **Versione .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali di debug](debugging-global-static-functions.md)
