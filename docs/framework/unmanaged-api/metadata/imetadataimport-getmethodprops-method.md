---
title: Metodo IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 3c7c3525f2f8753241c9a206e4cf5e552bf06efe
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503627"
---
# <a name="imetadataimportgetmethodprops-method"></a>Metodo IMetaDataImport::GetMethodProps
Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mb`  
 in Token MethodDef che rappresenta il metodo per il quale restituire i metadati.  
  
 `pClass`  
 out Puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.  
  
 `szMethod`  
 out Puntatore a un buffer con il nome del metodo.  
  
 `cchMethod`  
 in Dimensione richiesta di `szMethod` .  
  
 `pchMethod`  
 out Un puntatore alla dimensione in caratteri wide di `szMethod` o, nel caso di troncamento, il numero effettivo di caratteri wide nel nome del metodo.  
  
 `pdwAttr`  
 out Puntatore a qualsiasi flag associato al metodo.  
  
 `ppvSigBlob`  
 out Puntatore alla firma dei metadati binari del metodo.  
  
 `pcbSigBlob`  
 out Puntatore alla dimensione in byte di `ppvSigBlob` .  
  
 `pulCodeRVA`  
 out Puntatore all'indirizzo virtuale relativo del metodo.  
  
 `pdwImplFlags`  
 out Puntatore a tutti i flag di implementazione per il metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
