---
title: Metodo IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96c013cd3e45e4ede0cbc9f42bf511a2eb3fc12d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223589"
---
# <a name="imetadataimportgetrva-method"></a>Metodo IMetaDataImport::GetRVA
Ottiene l'indirizzo virtuale relativo (RVA) e i flag di implementazione del metodo o del campo rappresentato dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 [in] Un token MethodDef o FieldDef metadati che rappresenta l'oggetto di codice per restituire il RVA per. Se il token FieldDef, il campo deve essere una variabile globale.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo dell'oggetto codice rappresentato dal token.  
  
 `pdwImplFlags`  
 [out] Puntatore ai flag di implementazione del metodo. Questo valore è una maschera di bit di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione. Il valore di `pdwImplFlags` è valido solo se `tk` è un token MethodDef.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
