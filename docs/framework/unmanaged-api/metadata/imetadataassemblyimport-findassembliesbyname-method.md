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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177796"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Metodo IMetaDataAssemblyImport::FindAssembliesByName
Ottiene una matrice di `szAssemblyName` assembly con il parametro specificato, utilizzando le regole standard utilizzate da Common Language Runtime (CLR) per la risoluzione dei riferimenti.  
  
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
 [in] Directory radice in cui cercare l'assembly specificato. Se questo valore `null`è `FindAssembliesByName` impostato su , cercherà l'assembly solo nella Global Assembly Cache.  
  
 `szPrivateBin`  
 [in] Un elenco di sottodirectory delimitate da punti e virgola (ad esempio, "bin;bin2"), nella directory radice, in cui cercare l'assembly. Queste directory vengono esaminate in aggiunta a quelle specificate nelle regole di sondaggio predefinite.  
  
 `szAssemblyName`  
 [in] Nome dell'assembly da trovare. Il formato di questa stringa è definito <xref:System.Reflection.AssemblyName>nella pagina di riferimento della classe per .  
  
 `ppIUnk`  
 [in] Matrice di tipo [IUnknown](/cpp/atl/iunknown) in `IMetadataAssemblyImport` cui inserire i puntatori a interfaccia.  
  
 `cMax`  
 [fuori] Numero massimo di puntatori a interfaccia `ppIUnk`che è possibile inserire in .  
  
 `pcAssemblies`  
 [fuori] Numero di puntatori a interfaccia restituiti. Ovvero, il numero di puntatori `ppIUnk`a interfaccia effettivamente inseriti in .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`restituito con successo.|  
|`S_FALSE`|Non ci sono assembly.|  
  
## <a name="remarks"></a>Osservazioni  
 Dato il nome `FindAssembliesByName` di un assembly, il metodo trova l'assembly seguendo le regole standard per la risoluzione dei riferimenti all'assembly. Per ulteriori informazioni, vedere [Come il runtime individua gli assembly.](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) `FindAssembliesByName` consente al chiamante di configurare vari aspetti del contesto del sistema di risoluzione degli assembly, ad esempio la base dell'applicazione e il percorso di ricerca privato.  
  
 Il `FindAssembliesByName` metodo richiede che CLR venga inizializzato nel processo per richiamare la logica di risoluzione dell'assembly. Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) `FindAssembliesByName`(passaggio COINITEE_DEFAULT) prima di chiamare , quindi seguire una chiamata a [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`restituisce un puntatore [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) al file contenente il manifesto dell'assembly per il nome dell'assembly passato. Se il nome dell'assembly specificato non è completamente specificato (ad esempio, se non include una versione), è possibile che vengano restituiti più assembly.  
  
 `FindAssembliesByName`viene in genere utilizzato da un compilatore che tenta di trovare un assembly di riferimento in fase di compilazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
