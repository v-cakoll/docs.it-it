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
ms.openlocfilehash: a58e03875ec021b41479085fa9e27a4321ae965e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004352"
---
# <a name="imetadataemitdefineparam-method"></a>Metodo IMetaDataEmit::DefineParam
Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione del parametro.  
  
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
 in Token per il metodo di cui viene definito il parametro.  
  
 `ulParamSeq`  
 in Numero di sequenza del parametro.  
  
 `szName`  
 in Nome del parametro in formato Unicode.  
  
 `dwParamFlags`  
 in Flag per il parametro. Si tratta di una maschera di maschera di `CorParamAttr` valori.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** per il valore costante.  
  
 `pValue`  
 in Valore costante per il parametro.  
  
 `cchValue`  
 in Dimensione, in caratteri Unicode, di `pValue` .  
  
 `ppd`  
 out `mdParamDef`Token assegnato.  
  
## <a name="remarks"></a>Commenti  
 I valori di sequenza in `ulParamSeq` iniziano con 1 per i parametri. Il numero di sequenza di un valore restituito è 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
