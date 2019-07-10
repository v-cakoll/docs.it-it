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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f3883b0cd1b7aca6265b738eace483c81eb37b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760147"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Metodo IMetaDataAssemblyImport::GetFileProps
Ottiene le proprietà del file con la firma dei metadati specificato.  
  
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
 [in] Il `mdFile` token di metadati che rappresenta il file per cui ottenere le proprietà.  
  
 `szName`  
 [out] Il nome semplice del file.  
  
 `cchName`  
 [in] Le dimensioni, in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Numero di caratteri wide effettivamente restituiti nella `szName`.  
  
 `ppbHashValue`  
 [out] Puntatore al valore hash. Questo è l'hash, usando l'algoritmo SHA-1, del file.  
  
 `pcbHashValue`  
 [out] Il numero di caratteri wide nel valore restituito di hash.  
  
 `pdwFileFlags`  
 [out] Puntatore al flag che descrivono i metadati applicati a un file. Il valore dei flag è una combinazione di uno o più [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
