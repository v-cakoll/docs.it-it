---
title: Metodo IMetaDataAssemblyEmit::DefineFile
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176058"
---
# <a name="imetadataassemblyemitdefinefile-method"></a>Metodo IMetaDataAssemblyEmit::DefineFile
Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 [in] Nome del file da utilizzare.  
  
 `pbHashValue`  
 [in] Puntatore ai dati hash associati all'assembly.  
  
 `cbHashValue`  
 [in] Dimensione in byte `pbHashValue`di .  
  
 `dwFileFlags`  
 [in] Combinazione bit per `FileFlags` bit di valori che specificano le impostazioni delle proprietà.  
  
 `pmdf`  
 [fuori] Puntatore al token `File` restituito.  
  
## <a name="remarks"></a>Osservazioni  
 È `File` necessario definire una struttura di metadati per ogni file che faceva parte di questo assembly al momento della compilazione dell'assembly, escluso il file che contiene i metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
