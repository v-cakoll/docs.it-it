---
title: Metodo IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177894"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Metodo IMetaDataAssemblyEmit::DefineAssembly
Crea `Assembly` una struttura contenente i metadati per l'assembly specificato e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKey`  
 [in] Chiave pubblica che identifica l'editore dell'assembly oppure NULL se l'assembly non ha un nome con nome sicuro.  
  
 `cbPublicKey`  
 [in] Dimensione in byte `pbPublicKey`di .  
  
 `uHashAlgId`  
 [in] Identificatore dell'algoritmo hash da utilizzare per crittografare i file nell'assembly oppure NULL per specificare l'algoritmo SHA-1.  
  
 `szName`  
 [in] Nome di testo leggibile dell'assembly. Questo valore non deve superare i 1024 caratteri.  
  
 `pMetaData`  
 [in] Puntatore a un'istanza assemblyMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.  
  
 `dwAssemblyFlags`  
 [in] Combinazione di valori [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) che descrivono le funzionalità dell'assembly.  
  
 `pmda`  
 [fuori] Puntatore al token di metadati.  
  
## <a name="remarks"></a>Osservazioni  
 È `Assembly` possibile definire una sola struttura di metadati all'interno di un manifesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
