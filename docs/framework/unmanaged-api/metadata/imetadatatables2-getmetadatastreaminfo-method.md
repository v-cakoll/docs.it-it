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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0301506d591a3738ea403393236c2574d48a7cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593966"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>Metodo IMetaDataTables2::GetMetaDataStreamInfo
Ottiene il nome, dimensioni e contenuto del flusso di metadati in corrispondenza dell'indice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ix`  
 [in] L'indice del flusso di richiesta dei metadati.  
  
 `ppchName`  
 [out] Un puntatore al nome del flusso.  
  
 `ppv`  
 [out] Un puntatore al flusso di metadati.  
  
 `pcb`  
 [out] Le dimensioni, in byte, di `ppv`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
