---
title: Metodo IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 78c192f10f629a0c1316ae7af7fc774819f4de8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007481"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Metodo IMetaDataAssemblyImport::GetFileProps
Ottiene le proprietà del file con la firma dei metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdf`  
 in `mdFile`Token di metadati che rappresenta il file per il quale ottenere le proprietà.  
  
 `szName`  
 out Nome semplice del file.  
  
 `cchName`  
 in Dimensione, in caratteri wide, di `szName` .  
  
 `pchName`  
 out Numero di caratteri wide effettivamente restituiti in `szName` .  
  
 `ppbHashValue`  
 out Puntatore al valore hash. Si tratta dell'hash, usando l'algoritmo SHA-1, del file.  
  
 `pcbHashValue`  
 out Numero di caratteri wide nel valore hash restituito.  
  
 `pdwFileFlags`  
 out Puntatore ai flag che descrivono i metadati applicati a un file. Il valore dei flag è una combinazione di uno o più valori [CorFileFlags](corfileflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
