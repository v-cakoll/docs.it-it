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
ms.openlocfilehash: 05902436c09d082f90af01f48c7e918650317ce7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009418"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Metodo IMetaDataAssemblyImport::FindAssembliesByName
Ottiene una matrice di assembly con il `szAssemblyName` parametro specificato, utilizzando le regole standard utilizzate dal Common Language Runtime (CLR) per la risoluzione dei riferimenti.  
  
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
 in Directory radice in cui cercare l'assembly specificato. Se questo valore è impostato su `null` , `FindAssembliesByName` verrà cercato solo nell'global assembly cache per l'assembly.  
  
 `szPrivateBin`  
 in Elenco di sottodirectory delimitate da punto e virgola, ad esempio "bin; BIN2", nella directory radice in cui cercare l'assembly. Queste directory vengono verificate in aggiunta a quelle specificate nelle regole di probe predefinite.  
  
 `szAssemblyName`  
 in Nome dell'assembly da trovare. Il formato di questa stringa è definito nella pagina di riferimento della classe per <xref:System.Reflection.AssemblyName> .  
  
 `ppIUnk`  
 in Matrice di tipo [IUnknown](/cpp/atl/iunknown) in cui inserire i `IMetadataAssemblyImport` puntatori all'interfaccia.  
  
 `cMax`  
 out Numero massimo di puntatori di interfaccia che possono essere inseriti in `ppIUnk` .  
  
 `pcAssemblies`  
 out Numero di puntatori a interfaccia restituiti. Ovvero il numero di puntatori di interfaccia effettivamente posizionati in `ppIUnk` .  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`la restituzione è riuscita.|  
|`S_FALSE`|Nessun assembly.|  
  
## <a name="remarks"></a>Commenti  
 Dato il nome di un assembly, il `FindAssembliesByName` metodo trova l'assembly seguendo le regole standard per la risoluzione dei riferimenti ad assembly. Per ulteriori informazioni, vedere [come il runtime individua gli assembly](../../deployment/how-the-runtime-locates-assemblies.md). `FindAssembliesByName`consente al chiamante di configurare vari aspetti del contesto del resolver dell'assembly, ad esempio il percorso di ricerca privato e di base dell'applicazione.  
  
 Il `FindAssembliesByName` metodo richiede l'inizializzazione di CLR nel processo per richiamare la logica di risoluzione dell'assembly. Pertanto, è necessario chiamare [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passando COINITEE_DEFAULT) prima di chiamare `FindAssembliesByName` e quindi seguire con una chiamata a [CoUninitializeCor](../hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`Restituisce un puntatore [IMetaDataImport](imetadataimport-interface.md) al file contenente il manifesto dell'assembly per il nome dell'assembly passato. Se il nome dell'assembly specificato non è completamente specificato (ad esempio, se non include una versione), potrebbero essere restituiti più assembly.  
  
 `FindAssembliesByName`viene comunemente usato da un compilatore che tenta di trovare un assembly a cui si fa riferimento in fase di compilazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Modalità di individuazione degli assembly da parte del runtime](../../deployment/how-the-runtime-locates-assemblies.md)
- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
