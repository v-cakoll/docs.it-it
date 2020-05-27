---
title: Metodo IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009119"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>Metodo IMetaDataAssemblyImport::EnumAssemblyRefs
Enumera le `mdAssemblyRef` istanze definite nel manifesto dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore. Deve essere un valore null quando il `EnumAssemblyRefs` metodo viene chiamato per la prima volta.  
  
 `rAssemblyRefs`  
 out Enumerazione dei `mdAssemblyRef` token di metadati.  
  
 `cMax`  
 in Numero massimo di token che è possibile inserire nella `rAssemblyRefs` matrice.  
  
 `pcTokens`  
 out Numero di token effettivamente inseriti in `rAssemblyRefs` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs`la restituzione è riuscita.|  
|`S_FALSE`|Nessun token da enumerare. In questo caso, `pcTokens` è impostato su zero.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
