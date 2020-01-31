---
title: Metodo ICLRMetadataLocator::GetMetadata
ms.date: 03/30/2017
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
ms.openlocfilehash: 66b3934d000b4f000c368acb1f57c8fc82a5c453
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793617"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>Metodo ICLRMetadataLocator::GetMetadata
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare i metadati di un'immagine.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `imagePath`  
 in Stringa che specifica il percorso del file di immagine.  
  
 `imageTimestamp`  
 in Timestamp del file di immagine.  
  
 `imageSize`  
 in Dimensioni del file di immagine.  
  
 `mvid`  
 in Identificatore univoco globale dell'immagine.  
  
 `mdRva`  
 in Indirizzo RVA (relativo Virtual Address) dei metadati. L'indirizzo è relativo all'indirizzo di base dell'immagine.  
  
 `flags`  
 in Riservato per usi futuri.  
  
 `bufferSize`  
 in Dimensione del buffer in cui inserire i metadati.  
  
 `buffer`  
 out Buffer in cui inserire i metadati.  
  
 `dataSize`  
 out Dimensioni dei metadati restituiti.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRMetadataLocator](iclrmetadatalocator-interface.md)
