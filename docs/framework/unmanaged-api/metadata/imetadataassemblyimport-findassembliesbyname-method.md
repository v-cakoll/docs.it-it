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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39d9b4e69080e759a5a7d930f61abb3ba6160801
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486147"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Metodo IMetaDataAssemblyImport::FindAssembliesByName
Ottiene una matrice di assembly specificato `szAssemblyName` parametro, usando le regole standard utilizzate da common language runtime (CLR) per la risoluzione dei riferimenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Directory radice in cui cercare l'assembly specificato. Se questo valore è impostato su `null`, `FindAssembliesByName` Cerca solo nella global assembly cache l'assembly.  
  
 `szPrivateBin`  
 [in] Un elenco delle sottodirectory delimitato da punto e virgola (, ad esempio, "bin; bin2"), sotto la directory radice, in cui eseguire la ricerca dell'assembly. Queste directory subiscono oltre a quelli specificati nell'impostazione predefinita le regole di individuazione tramite probe.  
  
 `szAssemblyName`  
 [in] Il nome dell'assembly da trovare. Il formato di questa stringa è definito nella pagina di riferimento di classe per <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Matrice di tipo [IUnknown](/cpp/atl/iunknown) in cui inserire il `IMetadataAssemblyImport` puntatori a interfaccia.  
  
 `cMax`  
 [out] Il numero massimo di puntatori a interfaccia che può essere inserito in `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Il numero dei puntatori a interfaccia restituito. Vale a dire il numero dei puntatori a interfaccia effettivamente posizionati `ppIUnk`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` stato restituito correttamente.|  
|`S_FALSE`|Non esistono alcun assembly.|  
  
## <a name="remarks"></a>Note  
 Dato un nome dell'assembly, il `FindAssembliesByName` metodo trova l'assembly, seguendo le regole standard per la risoluzione dei riferimenti ad assembly. (Per altre informazioni, vedere [modo in cui il Runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` consente al chiamante configurare vari aspetti del contesto del resolver di assembly, ad esempio il percorso di ricerca di base e privata dell'applicazione.  
  
 Il `FindAssembliesByName` metodo richiesto a CLR di inizializzare il processo per richiamare la logica di risoluzione di assembly. Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName`, quindi seguire con una chiamata al [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Restituisce un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntatore del file contenente il manifesto dell'assembly per il nome dell'assembly che viene passato. Se il nome dell'assembly specificata non è completamente specificato (ad esempio, se non sono incluse una versione), potrebbe essere restituito più assembly.  
  
 `FindAssembliesByName` viene utilizzata solitamente da un compilatore che tenta di trovare un assembly di riferimento in fase di compilazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
