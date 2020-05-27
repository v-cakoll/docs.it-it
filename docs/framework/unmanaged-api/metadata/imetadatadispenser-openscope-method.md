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
ms.openlocfilehash: 8d9de753f1c44338a96e990def80643d591f2a8b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007468"
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
 in Nome del file da aprire. Il file deve contenere Common Language Runtime metadati (CLR).  
  
 `dwOpenFlags`  
 in Valore dell'enumerazione [CorOpenFlags](coropenflags-enumeration.md) per specificare la modalità (lettura, scrittura e così via) per l'apertura.  
  
 `riid`  
 in IID dell'interfaccia di metadati desiderata da restituire. il chiamante utilizzerà l'interfaccia per importare (leggere) o creare (scrivere) metadati.  
  
 Il valore di `riid` deve specificare una delle interfacce "Import" o "Emit". I valori validi sono IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 o IID_IMetaDataImport2.  
  
 `ppIUnk`  
 out Puntatore all'interfaccia restituita.  
  
## <a name="remarks"></a>Commenti  
 La copia in memoria dei metadati può essere sottoposta a query usando i metodi di una delle interfacce di "importazione" oppure aggiunti a usando i metodi di una delle interfacce "Emit".  
  
 Se il file di destinazione non contiene metadati CLR, il `OpenScope` metodo avrà esito negativo.  
  
 Nel .NET Framework versione 1,0 e la versione 1,1, se viene aperto un ambito con `dwOpenFlags` impostato su ofRead, è idoneo per la condivisione. Ovvero, se le chiamate successive `OpenScope` passano il nome di un file che è stato precedentemente aperto, l'ambito esistente viene riutilizzato e non viene creato un nuovo set di strutture di dati. Tuttavia, i problemi possono verificarsi a causa di questa condivisione.  
  
 Nella versione .NET Framework 2,0 gli ambiti aperti con `dwOpenFlags` impostato su ofRead non sono più condivisi. Usare il valore ofReadOnly per consentire la condivisione dell'ambito. Quando viene condiviso un ambito, le query che utilizzano le interfacce di metadati di "lettura/scrittura" avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
