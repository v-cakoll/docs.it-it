---
title: Metodo IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177648"
---
# <a name="imetadatadispenserdefinescope-method"></a>Metodo IMetaDataDispenser::DefineScope
Crea una nuova area in memoria in cui è possibile creare nuovi metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `rclsid`  
 [in] CLSID della versione delle strutture di metadati da creare. Questo valore deve essere CLSID_CorMetaDataRuntime per .NET Framework versione 2.0.  
  
 `dwCreateFlags`  
 [in] Flag che specificano le opzioni. Questo valore deve essere zero per .NET Framework 2.0.  
  
 `riid`  
 [in] IID dell'interfaccia di metadati desiderata da restituire; il chiamante utilizzerà l'interfaccia per creare i nuovi metadati.  
  
 Il valore `riid` di deve specificare una delle interfacce "emit". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit o IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 [fuori] Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Osservazioni  
 `DefineScope`crea un set di tabelle di metadati in memoria, genera un GUID univoco (identificatore di versione del modulo o MVID) per i metadati e crea una voce nella tabella del modulo per l'unità di compilazione generata.  
  
 È possibile associare attributi all'ambito dei metadati nel suo complesso utilizzando il [metodo IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) o [IMetaDataEmit::DefineCustomAttribute,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) in base alle esigenze.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
