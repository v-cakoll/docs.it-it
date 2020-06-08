---
title: Metodo IMetaDataImport2::EnumGenericParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 093e3edf0a3c06222ebc56a4876fca08d1b7578f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490729"
---
# <a name="imetadataimport2enumgenericparams-method"></a>Metodo IMetaDataImport2::EnumGenericParams
Ottiene un enumeratore per una matrice di token di parametro generici associati al token TypeDef o MethodDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore.  
  
 `tk`  
 in Token TypeDef o MethodDef i cui parametri generici devono essere enumerati.  
  
 `rGenericParams`  
 out Matrice di parametri generici da enumerare.  
  
 `cMax`  
 in Numero massimo di token richiesto da inserire in `rGenericParams` .  
  
 `pcGenericParams`  
 out Numero restituito di token inseriti in `rGenericParams` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams`la restituzione è riuscita.|  
|`S_FALSE`|`phEnum`non contiene elementi Member. In questo caso, `pcGenericParams` è impostato su 0 (zero).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
