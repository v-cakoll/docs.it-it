---
title: Metodo IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74d0c2e9777a7bd3d49622fb326ecb6b58fbec07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782540"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>Metodo IMetaDataImport::EnumUnresolvedMethods
Enumera i token MemberDef che rappresentano i metodi non risolti nell'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Un puntatore all'enumeratore. Per la prima chiamata di questo metodo deve essere NULL.  
  
 `rMethods`  
 [out] Matrice utilizzata per archiviare i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMethods`.  
  
 `pcTokens`  
 [out] Il numero di token MemberDef restituiti in `rMethods`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` stato restituito correttamente.|  
|`S_FALSE`|Non sono presenti token da enumerare. In tal caso, `pcTokens` è uguale a zero.|  
  
## <a name="remarks"></a>Note  
 Un metodo non risolto è quello che è stata dichiarata ma non implementato. Un metodo è incluso nell'enumerazione se il metodo è contrassegnato `miForwardRef` e il valore `mdPinvokeImpl` o `miRuntime` è impostato su zero. In altre parole, un metodo non risolto è un metodo di classe contrassegnato `miForwardRef` ma che non viene implementato in codice non gestito (raggiunto tramite PInvoke) né implementati internamente dal runtime stesso.  
  
 L'enumerazione esclude tutti i metodi definiti nell'ambito del modulo (variabili globali) o in classi astratte o interfacce.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
