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
ms.openlocfilehash: 1232e8c574f263f709a9b66c7b1b3d06cca5e4da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
#### <a name="parameters"></a>Parametri  
 `tk`  
 [in] Token di metadati MethodDef o FieldDef che rappresenta l'oggetto di codice per il quale restituire per. Se il token FieldDef, il campo deve essere una variabile globale.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo dell'oggetto codice rappresentato dal token.  
  
 `pdwImplFlags`  
 [out] Puntatore ai flag di implementazione per il metodo. Questo valore è una maschera di bit di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione. Il valore di `pdwImplFlags` è valido solo se `tk` è un token MethodDef.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
