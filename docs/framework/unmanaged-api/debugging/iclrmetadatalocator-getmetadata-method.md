---
title: Metodo ICLRMetadataLocator::GetMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8758a96464d1465d92fb17314f1e36ab8d9169c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>Metodo ICLRMetadataLocator::GetMetadata
Chiamato dai servizi di accesso ai dati di common language runtime (CLR) per recuperare i metadati di un'immagine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `imagePath`  
 [in] Stringa che specifica il percorso del file di immagine.  
  
 `imageTimestamp`  
 [in] Il timestamp del file di immagine.  
  
 `imageSize`  
 [in] Le dimensioni del file di immagine.  
  
 `mvid`  
 [in] Identificatore univoco globale dell'immagine.  
  
 `mdRva`  
 [in] L'indirizzo virtuale relativo (RVA) dei metadati. L'indirizzo è relativo all'indirizzo di base di immagine.  
  
 `flags`  
 [in] Riservato per utilizzi futuri.  
  
 `bufferSize`  
 [in] Le dimensioni del buffer in cui inserire i metadati.  
  
 `buffer`  
 [out] Buffer in cui inserire i metadati.  
  
 `dataSize`  
 [out] Le dimensioni dei metadati che viene restituito.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, Clrdata. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRMetadataLocator](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
