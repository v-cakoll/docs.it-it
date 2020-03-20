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
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175902"
---
# <a name="imetadatadispenserexsetoption-method"></a>Metodo IMetaDataDispenserEx::SetOption
Imposta l'opzione specificata su un valore specificato per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `optionId`  
 [in] Puntatore a un GUID che specifica l'opzione da impostare.  
  
 `pValue`  
 [in] Valore da utilizzare per impostare l'opzione. Il tipo di questo valore deve essere una variante del tipo di opzione specificata.  
  
## <a name="remarks"></a>Osservazioni  
 Nella tabella seguente sono elencati `optionId` i GUID disponibili a cui il `pValue` parametro può puntare e i valori validi corrispondenti per il parametro.  
  
|GUID|Descrizione|`pValue`Parametro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controlla quali elementi vengono controllati per i duplicati. Ogni volta che si chiama un metodo [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) che crea un nuovo elemento, è possibile chiedere al metodo di verificare se l'elemento esiste già nell'ambito corrente. Ad esempio, è possibile verificare l'esistenza di `mdMethodDef` elementi; In questo caso, quando si chiama [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), verrà verificato che il metodo non esista già nell'ambito corrente. Questo controllo utilizza la chiave che identifica in modo univoco un determinato metodo: tipo padre, nome e firma.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorCheckDuplicatesFor.](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md)|  
|MetaDataRefToDefCheck|Controlli degli elementi di riferimento convertiti in definizioni. Per impostazione predefinita, il motore dei metadati ottimizzerà il codice convertendo un elemento di riferimento nella relativa definizione se l'elemento a cui si fa riferimento è effettivamente definito nell'ambito corrente.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorRefToDefCheck.](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md)|  
|MetaDataNotificationForTokenMovement|Controlla quali rimappature di token che si verificano durante un'unione di metadati generano callback. Utilizzare il metodo [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) per stabilire l'interfaccia [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) .|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorNotificationForTokenMovement.](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md)|  
|MetaDataSetENC|Controlla il comportamento di edit-and-continue (ENC). È possibile impostare una sola modalità di comportamento alla volta.|Deve essere una variante del tipo UI4 e deve contenere un valore dell'enumerazione [CorSetENC.](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) Il valore non è una maschera di bit.|  
|MetaDataErrorIfEmitOutOfOrder|I controlli che emettevano errori non in ordine generano callback. L'emissione di metadati non in ordine non è irreversibile; Tuttavia, se si generano metadati in un ordine preferito dal motore dei metadati, i metadati sono più compatti e pertanto possono essere ricercati in modo più efficiente. Utilizzare `IMetaDataEmit::SetHandler` il metodo per stabilire l'interfaccia [IMetaDataError.](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorErrorIfEmitOutOfOrder.](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md)|  
|MetaDataImportOption (Opzione MetaDataImportOption)|Controlla quali tipi di elementi eliminati durante un'eNC vengono recuperati da un enumeratore.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorImportOptions.](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md)|  
|MetaDataThreadSafetyOptions|Controlla se il motore dei metadati ottiene i blocchi di lettura/scrittura, garantendo in tal modo la thread safety. Per impostazione predefinita, il motore presuppone che l'accesso sia a thread singolo dal chiamante, pertanto non vengono ottenuti blocchi. I client sono responsabili della corretta sincronizzazione dei thread quando si utilizza l'API dei metadati.|Deve essere una variante del tipo UI4 e deve contenere un valore dell'enumerazione [CorThreadSafetyOptions.](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) Il valore non è una maschera di bit.|  
|MetaDataGenerateTCEAdapter|Controlla se l'utilità di importazione della libreria dei tipi deve generare le schede degli eventi ad accoppiamento ridotto (TCE) per i contenitori dei punti di connessione COM.|Deve essere una variante di tipo BOOL. Se `pValue` è `true`impostato su , l'utilità di importazione della libreria dei tipi genera le schede TCE.|  
|MetaDataTypeLibImportNamespace|Specifica uno spazio dei nomi non predefinito per la libreria dei tipi che viene importata.|Deve essere un valore null o una variante di tipo BSTR. Se `pValue` è un valore null, lo spazio dei nomi corrente è impostato su null; in caso contrario, lo spazio dei nomi corrente viene impostato sulla stringa contenuta nel tipo BSTR della variante.|  
|MetaDataLinkerOpzioni|Controlla se il linker deve generare un assembly o un file di modulo .NET Framework.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori dell'enumerazione [CorLinkerOptions.](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md)|  
|MetaDataRuntimeVersion|Specifica la versione di Common Language Runtime rispetto alla quale è stata compilata l'immagine. La versione viene archiviata come stringa, ad esempio "v1.0.3705".|Deve essere un valore null, un valore VT_EMPTY o una variante di tipo BSTR. Se `pValue` è null, la versione di runtime è impostata su null. Se `pValue` viene VT_EMPTY, la versione viene impostata su un valore predefinito, che viene ricavato dalla versione di Mscorwks.dll all'interno della quale viene eseguito il codice dei metadati. In caso contrario, la versione del runtime viene impostata sulla stringa che è contenuta nel tipo BSTR della variante.|  
|MetaDataMergerOptions|Specifica le opzioni per l'unione dei metadati.|Deve essere una variante del tipo UI4 e deve `MergeFlags` contenere una combinazione dei valori dell'enumerazione, descritta nel file CorHdr.h.|  
|MetaDataPreserveLocalRefs|Disabilita l'ottimizzazione dei riferimenti locali nelle definizioni.|Deve contenere una combinazione dei valori dell'enumerazione [CorLocalRefPreservation.](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md)|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
