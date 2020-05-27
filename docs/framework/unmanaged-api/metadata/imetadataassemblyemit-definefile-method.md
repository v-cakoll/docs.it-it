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
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008144"
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
 in Nome del file da utilizzare.  
  
 `pbHashValue`  
 in Puntatore ai dati hash associati all'assembly.  
  
 `cbHashValue`  
 in Dimensioni in byte di `pbHashValue` .  
  
 `dwFileFlags`  
 in Combinazione bit per bit di `FileFlags` valori che specificano le impostazioni delle proprietà.  
  
 `pmdf`  
 out Puntatore al `File` token restituito.  
  
## <a name="remarks"></a>Commenti  
 È `File` necessario definire una struttura di metadati per ogni file che faceva parte di questo assembly nel momento in cui l'assembly è stato compilato, escluso il file contenente i metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
