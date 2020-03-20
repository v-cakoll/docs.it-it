---
title: Metodo IMetaDataEmit::DefineParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177699"
---
# <a name="imetadataemitdefineparam-method"></a>Metodo IMetaDataEmit::DefineParam
Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per tale definizione di parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>Parametri  
 `md`  
 [in] Token per il metodo il cui parametro viene definito.  
  
 `ulParamSeq`  
 [in] Numero di sequenza del parametro.  
  
 `szName`  
 [in] Nome del parametro in Unicode.  
  
 `dwParamFlags`  
 [in] Flag per il parametro. Si tratta di `CorParamAttr` una maschera di bit di valori.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` per il valore *\** costante.  
  
 `pValue`  
 [in] Valore costante per il parametro.  
  
 `cchValue`  
 [in] La dimensione, in caratteri `pValue`Unicode, di .  
  
 `ppd`  
 [fuori] Token `mdParamDef` assegnato.  
  
## <a name="remarks"></a>Osservazioni  
 I valori `ulParamSeq` di sequenza iniziano con 1 per i parametri. Un valore restituito ha un numero di sequenza pari a 0.A return value has a sequence number of 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
