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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cfe600b54eb03a07ea01375355c5ff94190e5d9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatadispenserexsetoption-method"></a>Metodo IMetaDataDispenserEx::SetOption
Imposta l'opzione specificata per un determinato valore per l'ambito dei metadati corrente. L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `optionId`  
 [in] Puntatore a un GUID che specifica l'opzione da impostare.  
  
 `pValue`  
 [in] Il valore da utilizzare per impostare l'opzione. Il tipo di questo valore deve essere una variante del tipo dell'opzione specificata.  
  
## <a name="remarks"></a>Note  
 La tabella seguente elenca i GUID disponibili che il `optionId` parametro può puntare e i corrispondenti valori validi per il `pValue` parametro.  
  
|GUID|Descrizione|`pValue` Parametro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controlla gli elementi selezionati per i duplicati. Ogni volta che si chiama un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) metodo che crea un nuovo elemento, è possibile chiedere al metodo per verificare se l'elemento esiste già nell'ambito corrente. Ad esempio, è possibile verificare l'esistenza di `mdMethodDef` elementi; in questo caso, quando si chiama [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), verificherà che il metodo non esiste già nell'ambito corrente. Questo controllo viene utilizzata la chiave che identifica in modo univoco un determinato metodo: padre di tipo, nome e firma.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enumerazione.|  
|MetaDataRefToDefCheck|I controlli che fa riferimento a elementi vengono convertiti in definizioni. Per impostazione predefinita, il motore dei metadati consente di ottimizzare il codice mediante la conversione di un elemento di cui si fa riferimento alla relativa definizione se l'elemento di riferimento viene effettivamente definita nell'ambito corrente.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enumerazione.|  
|MetaDataNotificationForTokenMovement|Determina quale token avvenuti durante un'unione di metadati generano callback. Utilizzare il [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) metodo per stabilire il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enumerazione.|  
|MetaDataSetENC|Controlla il comportamento di modifica e continuazione (ENC). Contemporaneamente, è possibile impostare solo una modalità di comportamento.|Deve essere una variante del tipo UI4 e deve contenere un valore di [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enumerazione. Il valore non è una maschera di bit.|  
|MetaDataErrorIfEmitOutOfOrder|Controlla i callback di generare gli errori generati out-di-ordine. Emissione di metadati non in ordine non è un errore irreversibile. Tuttavia, se si generano metadati in un ordine preferito dal motore di metadati, i metadati sono più compatto e pertanto possono eseguire in modo più efficiente la ricerca. Utilizzare il `IMetaDataEmit::SetHandler` metodo per stabilire il [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) interfaccia.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enumerazione.|  
|MetaDataImportOption|Controlla quali tipi di elementi che sono stati eliminati durante un ENC vengono recuperati dall'enumeratore.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [Enumerazione CorImportOptions](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enumerazione.|  
|MetaDataThreadSafetyOptions|Controlla se il motore dei metadati ottiene blocchi, per garantirne la sicurezza dei thread di lettura/scrittura. Per impostazione predefinita, il motore si presuppone che l'accesso a thread singolo dal chiamante, non vengono ottenuti blocchi. I client sono responsabili della gestione della sincronizzazione di thread appropriato quando si utilizza l'API dei metadati.|Deve essere una variante del tipo UI4 e deve contenere un valore di [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enumerazione. Il valore non è una maschera di bit.|  
|MetaDataGenerateTCEAdapters|Determina se l'utilità di importazione della libreria di tipo deve generare le schede evento accoppiamento (TCE) per i contenitori di punto di connessione COM.|Deve essere una variante del tipo BOOL. Se `pValue` è impostato su `true`, type library importer genera gli adattatori TCE.|  
|MetaDataTypeLibImportNamespace|Specifica uno spazio dei nomi non predefinito per la libreria dei tipi da importare.|Deve essere un valore null o una variante del tipo BSTR. Se `pValue` è un valore null, lo spazio dei nomi corrente è impostato su null; in caso contrario, lo spazio dei nomi corrente viene impostato sulla stringa contenuta nel tipo BSTR della variante.|  
|MetaDataLinkerOptions|Determina se il linker deve generare un assembly o un file di modulo .NET Framework.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enumerazione.|  
|MetaDataRuntimeVersion|Specifica la versione di common language runtime con cui è stata compilata questa immagine. La versione viene archiviata come una stringa, ad esempio "v 1.0.3705".|Deve essere un valore null, un valore VT_EMPTY o una variante del tipo BSTR. Se `pValue` è null, la versione di runtime è impostata su null. Se `pValue` è VT_EMPTY, la versione è impostata su un valore predefinito, che viene disegnato dalla versione di Mscorwks.dll all'interno del quale è in esecuzione il codice dei metadati. In caso contrario, la versione di runtime è impostata per la stringa contenuta nel tipo BSTR della variante.|  
|MetaDataMergerOptions|Specifica le opzioni per l'unione dei metadati.|Deve essere una variante del tipo UI4 e deve contenere una combinazione dei valori del `MergeFlags` enumerazione, è descritto nel file corhdr. H.|  
|MetaDataPreserveLocalRefs|Disabilita l'ottimizzazione locali riferimenti nelle definizioni.|Deve contenere una combinazione dei valori del [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enumerazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [Interfaccia IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
