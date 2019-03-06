---
title: Metodo IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67447e90198ded258645ad7d9173eed37bb60915
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479415"
---
# <a name="imetadataimportgetclasslayout-method"></a>Metodo IMetaDataImport::GetClassLayout
Ottiene le informazioni sul layout per la classe a cui fa riferimento il token TypeDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token TypeDef per la classe con il layout da restituire.  
  
 `pdwPackSize`  
 [out] Uno dei valori 1, 2, 4, 8 o 16, che rappresenta la dimensione di compressione della classe.  
  
 `rFieldOffset`  
 [out] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) valori.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rFieldOffset`.  
  
 `pcFieldOffset`  
 [out] Il numero di elementi restituiti nella `rFieldOffset`.  
  
 `pulClassSize`  
 [out] La dimensione in byte della classe rappresentata da `td`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
