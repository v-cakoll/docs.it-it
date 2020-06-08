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
ms.openlocfilehash: c991c0af845bc6825db6b3bf258fe0809d5db804
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503696"
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
 [in, out] Puntatore all'enumeratore. Deve essere NULL per la prima chiamata di questo metodo.  
  
 `rMethods`  
 out Matrice utilizzata per archiviare i token MemberDef.  
  
 `cMax`  
 [in] Dimensione massima della matrice `rMethods`.  
  
 `pcTokens`  
 out Numero di token MemberDef restituiti in `rMethods` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods`la restituzione è riuscita.|  
|`S_FALSE`|Nessun token da enumerare. In tal caso, `pcTokens` è zero.|  
  
## <a name="remarks"></a>Osservazioni  
 Un metodo non risolto è uno che è stato dichiarato ma non implementato. Un metodo è incluso nell'enumerazione se il metodo è contrassegnato `miForwardRef` e `mdPinvokeImpl` o `miRuntime` è impostato su zero. In altre parole, un metodo non risolto è un metodo della classe contrassegnato `miForwardRef` ma non implementato nel codice non gestito (raggiunto tramite PInvoke), né internamente dal runtime stesso  
  
 L'enumerazione esclude tutti i metodi definiti nell'ambito del modulo (Globals) o in interfacce o classi astratte.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
