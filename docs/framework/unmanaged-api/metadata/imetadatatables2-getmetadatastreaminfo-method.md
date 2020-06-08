---
title: Metodo IMetaDataTables2::GetMetaDataStreamInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 7d39d089c348b7320651ed21ea14ba07d7877fd4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501095"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>Metodo IMetaDataTables2::GetMetaDataStreamInfo
Ottiene il nome, le dimensioni e il contenuto del flusso di metadati in corrispondenza dell'indice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ix`  
 in Indice del flusso di metadati richiesto.  
  
 `ppchName`  
 out Puntatore al nome del flusso.  
  
 `ppv`  
 out Puntatore al flusso di metadati.  
  
 `pcb`  
 out Dimensione, in byte, di `ppv` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables2](imetadatatables2-interface.md)
- [Interfaccia IMetaDataTables](imetadatatables-interface.md)
