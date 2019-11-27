---
title: Metodo IMetaDataAssemblyImport::FindAssembliesByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c12d3a7a7d1e52529435361aa12e22e4edeecf03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448298"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Metodo IMetaDataAssemblyImport::FindAssembliesByName
Ottiene una matrice di assembly con il parametro di `szAssemblyName` specificato, utilizzando le regole standard utilizzate dall'Common Language Runtime (CLR) per la risoluzione dei riferimenti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szAppBase`  
 in Directory radice in cui cercare l'assembly specificato. Se questo valore è impostato su `null`, `FindAssembliesByName` verrà cercato solo nel Global Assembly Cache per l'assembly.  
  
 `szPrivateBin`  
 in Elenco di sottodirectory delimitate da punto e virgola, ad esempio "bin; BIN2", nella directory radice in cui cercare l'assembly. Queste directory vengono verificate in aggiunta a quelle specificate nelle regole di probe predefinite.  
  
 `szAssemblyName`  
 in Nome dell'assembly da trovare. Il formato di questa stringa viene definito nella pagina di riferimento della classe per <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 in Matrice di tipo [IUnknown](/cpp/atl/iunknown) in cui inserire i puntatori dell'interfaccia `IMetadataAssemblyImport`.  
  
 `cMax`  
 out Numero massimo di puntatori a interfaccia che è possibile inserire in `ppIUnk`.  
  
 `pcAssemblies`  
 out Numero di puntatori a interfaccia restituiti. Ovvero il numero di puntatori di interfaccia effettivamente posizionati in `ppIUnk`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` ha restituito un esito positivo.|  
|`S_FALSE`|Nessun assembly.|  
  
## <a name="remarks"></a>Osservazioni  
 Dato il nome di un assembly, il metodo `FindAssembliesByName` trova l'assembly seguendo le regole standard per la risoluzione dei riferimenti ad assembly. Per ulteriori informazioni, vedere [come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md). `FindAssembliesByName` consente al chiamante di configurare vari aspetti del contesto del resolver di assembly, ad esempio il percorso di ricerca privato e di base dell'applicazione.  
  
 Il metodo `FindAssembliesByName` richiede l'inizializzazione di CLR nel processo per richiamare la logica di risoluzione dell'assembly. Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName`e quindi seguire una chiamata a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` restituisce un puntatore [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) al file contenente il manifesto dell'assembly per il nome dell'assembly passato. Se il nome dell'assembly specificato non è completamente specificato (ad esempio, se non include una versione), potrebbero essere restituiti più assembly.  
  
 `FindAssembliesByName` viene comunemente usato da un compilatore che tenta di trovare un assembly a cui si fa riferimento in fase di compilazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
