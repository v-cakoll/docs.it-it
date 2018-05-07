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
ms.openlocfilehash: a6c7bf332d829a440fe216756f7a23ec1277e6c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Metodo IMetaDataAssemblyImport::FindAssembliesByName
Ottiene una matrice di assembly con l'oggetto specificato `szAssemblyName` parametro, utilizzando le regole standard utilizzate da common language runtime (CLR) per la risoluzione dei riferimenti.  
  
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
  
#### <a name="parameters"></a>Parametri  
 `szAppBase`  
 [in] La directory radice in cui eseguire la ricerca per l'assembly specificato. Se questo valore è impostato su `null`, `FindAssembliesByName` verranno ricercati solo nella global assembly cache l'assembly.  
  
 `szPrivateBin`  
 [in] Elenco delimitato da punto e virgola sottodirectory (ad esempio, "bin; bin2"), la directory radice, in cui eseguire la ricerca dell'assembly. Queste directory subiscono oltre a quelli specificati nelle regole di ricerca predefinite.  
  
 `szAssemblyName`  
 [in] Il nome dell'assembly da trovare. Il formato di questa stringa è definito nella pagina di riferimento di classe per <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Matrice di tipo <<!--zzxref:IUnknown --> `IUnknown`> in cui inserire il `IMetadataAssemblyImport` i puntatori a interfaccia.  
  
 `cMax`  
 [out] Il numero massimo di puntatori a interfaccia che può essere inserita in `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Il numero di puntatori a interfaccia restituito. Vale a dire il numero di puntatori a interfaccia effettivamente inseriti in `ppIUnk`.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` stato restituito correttamente.|  
|`S_FALSE`|Non esistono alcun assembly.|  
  
## <a name="remarks"></a>Note  
 Dato un nome di assembly, il `FindAssembliesByName` metodo individua l'assembly seguendo le regole per la risoluzione di riferimenti ad assembly standard. (Per ulteriori informazioni, vedere [come il Runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` consente al chiamante di configurare diversi aspetti del contesto di sistema di risoluzione assembly, ad esempio il percorso di ricerca privato e base dell'applicazione.  
  
 Il `FindAssembliesByName` metodo richiede l'inizializzazione del processo per richiamare la logica di risoluzione assembly CLR. Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName`, quindi seguire con una chiamata a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Restituisce un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) puntatore del file contenente il manifesto dell'assembly per il nome dell'assembly passato. Se il nome di assembly specificato non è completamente specificato (ad esempio, se non include una versione), che vengano restituiti più assembly.  
  
 `FindAssembliesByName` è comunemente utilizzate da un compilatore che tenta di individuare un assembly di riferimento in fase di compilazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
