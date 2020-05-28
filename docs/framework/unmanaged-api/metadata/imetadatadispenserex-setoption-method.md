---
title: Metodo IMetaDataDispenserEx::SetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: 0cb0dee7db7faa4c1324d705218934489ec6a4b6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005856"
---
# <a name="imetadatadispenserexsetoption-method"></a>Metodo IMetaDataDispenserEx::SetOption
Imposta l'opzione specificata su un valore specificato per l'ambito dei metadati corrente. L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `optionId`  
 in Puntatore a un GUID che specifica l'opzione da impostare.  
  
 `pValue`  
 in Valore da utilizzare per impostare l'opzione. Il tipo di questo valore deve essere una variante del tipo dell'opzione specificata.  
  
## <a name="remarks"></a>Commenti  
 Nella tabella seguente sono elencati i GUID disponibili a cui il `optionId` parametro può puntare e i valori validi corrispondenti per il `pValue` parametro.  
  
|GUID|Descrizione|`pValue`Parametro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controlla gli elementi di cui verificare la presenza di duplicati. Ogni volta che si chiama un metodo [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) per la creazione di un nuovo elemento, è possibile chiedere al metodo di controllare se l'elemento esiste già nell'ambito corrente. Ad esempio, è possibile verificare l'esistenza di `mdMethodDef` elementi. in questo caso, quando si chiama [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), viene verificato che il metodo non esista già nell'ambito corrente. Questo controllo Usa la chiave che identifica in modo univoco un metodo specifico: tipo padre, nome e firma.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorCheckDuplicatesFor](corcheckduplicatesfor-enumeration.md) .|  
|MetaDataRefToDefCheck|Controlla quali elementi a cui si fa riferimento vengono convertiti in definizioni. Per impostazione predefinita, il motore dei metadati ottimizza il codice convertendo un elemento a cui si fa riferimento nella definizione se l'elemento a cui si fa riferimento è effettivamente definito nell'ambito corrente.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorRefToDefCheck](correftodefcheck-enumeration.md) .|  
|MetaDataNotificationForTokenMovement|Controlla quali rimappe del token che si verificano durante un'Unione di metadati generano callback. Usare il metodo [IMetaDataEmit::](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) SetValue per stabilire l'interfaccia [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) .|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorNotificationForTokenMovement](cornotificationfortokenmovement-enumeration.md) .|  
|MetaDataSetENC|Controlla il comportamento di modifica e continuazione (ENC). È possibile impostare una sola modalità di comportamento alla volta.|Deve essere una variante di tipo UI4 e deve contenere un valore dell'enumerazione [CorSetENC](corsetenc-enumeration.md) . Il valore non è una maschera di maschera.|  
|MetaDataErrorIfEmitOutOfOrder|I controlli che generano errori non ordinati generano i callback. L'emissione di metadati non ordinati non è irreversibile. Tuttavia, se si generano metadati in un ordine favorito dal motore dei metadati, i metadati sono più compatti e pertanto possono essere cercati in modo più efficiente. Usare il `IMetaDataEmit::SetHandler` metodo per stabilire l'interfaccia [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) .|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorErrorIfEmitOutOfOrder](corerrorifemitoutoforder-enumeration.md) .|  
|MetaDataImportOption|Controlla quali tipi di elementi sono stati eliminati durante un'operazione ENC vengono recuperati da un enumeratore.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione Enumerazione [CorImportOptions](corimportoptions-enumeration.md) .|  
|MetaDataThreadSafetyOptions|Controlla se il motore dei metadati ottiene i blocchi reader/writer, garantendo in tal modo thread safety. Per impostazione predefinita, il motore presuppone che l'accesso sia a thread singolo dal chiamante, quindi non viene ottenuto alcun blocco. I client hanno la responsabilità di mantenere la sincronizzazione dei thread corretta quando si usa l'API dei metadati.|Deve essere una variante di tipo UI4 e deve contenere un valore dell'enumerazione [CorThreadSafetyOptions](corthreadsafetyoptions-enumeration.md) . Il valore non è una maschera di maschera.|  
|MetaDataGenerateTCEAdapters|Controlla se l'utilità di importazione della libreria dei tipi deve generare gli adapter per gli eventi strettamente associati per i contenitori dei punti di connessione COM.|Deve essere una variante di tipo BOOL. Se `pValue` è impostato su `true` , l'utilità di importazione della libreria dei tipi genera le schede TCE.|  
|MetaDataTypeLibImportNamespace|Specifica uno spazio dei nomi non predefinito per la libreria dei tipi da importare.|Deve essere un valore null o una variante di tipo BSTR. Se `pValue` è un valore null, lo spazio dei nomi corrente è impostato su null; in caso contrario, lo spazio dei nomi corrente viene impostato sulla stringa mantenuta nel tipo BSTR della variante.|  
|MetaDataLinkerOptions|Controlla se il linker deve generare un assembly o un file di modulo .NET Framework.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorLinkerOptions](corlinkeroptions-enumeration.md) .|  
|MetaDataRuntimeVersion|Specifica la versione del Common Language Runtime in cui è stata compilata l'immagine. La versione viene archiviata come stringa, ad esempio "v 1.0.3705".|Deve essere un valore null, un valore VT_EMPTY o una variante di tipo BSTR. Se `pValue` è null, la versione del runtime è impostata su null. Se `pValue` è VT_EMPTY, la versione è impostata su un valore predefinito, che viene disegnato dalla versione di mscorwks. dll all'interno della quale è in esecuzione il codice dei metadati. In caso contrario, la versione del runtime viene impostata sulla stringa mantenuta nel tipo BSTR della variante.|  
|MetaDataMergerOptions|Specifica le opzioni per l'Unione dei metadati.|Deve essere una variante di tipo UI4 e deve contenere una combinazione dei valori dell' `MergeFlags` enumerazione, descritta nel file corhdr. h.|  
|MetaDataPreserveLocalRefs|Disabilita l'ottimizzazione dei riferimenti locali nelle definizioni.|Deve contenere una combinazione dei valori dell'enumerazione [CorLocalRefPreservation](corlocalrefpreservation-enumeration.md) .|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](imetadatadispenser-interface.md)
