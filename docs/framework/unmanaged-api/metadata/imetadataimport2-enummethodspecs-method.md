---
title: Metodo IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 8f6fbc570e7ea85aca5b365611d58a1700fb27cd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490718"
---
# <a name="imetadataimport2enummethodspecs-method"></a>Metodo IMetaDataImport2::EnumMethodSpecs
Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a>Parametri  
 `phEnum`  
 [in, out] Puntatore all'enumeratore per `rMethodSpecs` .  
  
 `tk`  
 in Token MemberRef o MethodDef che rappresenta il metodo i cui token MethodSpec devono essere enumerati. Se il valore di `tk` è 0 (zero), verranno enumerati tutti i token MethodSpec nell'ambito.  
  
 `rMethodSpecs`  
 out Matrice di token MethodSpec da enumerare.  
  
 `cMax`  
 in Numero massimo di token richiesto da inserire in `rMethodSpecs` .  
  
 `pcMethodSpecs`  
 out Numero restituito di token inseriti in `rMethodSpecs` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`la restituzione è riuscita.|  
|`S_FALSE`|`phEnum`non contiene elementi Member. In questo caso, `pcMethodSpecs` è impostato su 0 (zero).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
