---
title: Metodo IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175941"
---
# <a name="imetadatadispenseropenscope-method"></a>Metodo IMetaDataDispenser::OpenScope
Apre un file su disco esistente ed esegue il mapping dei relativi metadati in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szScope`  
 [in] Nome del file da aprire. Il file deve contenere metadati CLR (Common Language Runtime).  
  
 `dwOpenFlags`  
 [in] Valore dell'enumerazione [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.  
  
 `riid`  
 [in] IID dell'interfaccia di metadati desiderata da restituire; il chiamante utilizzerà l'interfaccia per importare (leggere) o generare (scrivere) metadati.  
  
 Il valore `riid` di deve specificare una delle interfacce "import" o "emit". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 [fuori] Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Osservazioni  
 La copia in memoria dei metadati può essere interrogata utilizzando metodi da una delle interfacce "import" o aggiunta all'utilizzo di metodi da una delle interfacce "emit".  
  
 Se il file di destinazione non `OpenScope` contiene metadati CLR, il metodo avrà esito negativo.  
  
 In .NET Framework versione 1.0 e 1.1, se `dwOpenFlags` un ambito viene aperto con impostato su ofRead, è idoneo per la condivisione. Ovvero, se le `OpenScope` chiamate successive pass-in di me di un file precedentemente aperto, l'ambito esistente viene riutilizzato e non viene creato un nuovo set di strutture di dati. Tuttavia, possono sorgere problemi a causa di questa condivisione.  
  
 In .NET Framework versione 2.0 gli `dwOpenFlags` ambiti aperti con impostato su ofRead non sono più condivisi. Utilizzare il valore ofReadOnly per consentire la condivisione dell'ambito. Quando un ambito è condiviso, le query che utilizzano interfacce di metadati "lettura/scrittura" avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
