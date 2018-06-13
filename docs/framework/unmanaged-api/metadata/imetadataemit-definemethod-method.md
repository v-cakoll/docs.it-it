---
title: Metodo IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53fd830cdefda58d40f96f8662a80d1888d963dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449199"
---
# <a name="imetadataemitdefinemethod-method"></a>Metodo IMetaDataEmit::DefineMethod
Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token per tale definizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il `mdTypedef` token della classe padre o dell'interfaccia padre del metodo. Impostare `td` a `mdTokenNil`, se si definisce una funzione globale.  
  
 `szName`  
 [in] Il nome del membro in formato Unicode.  
  
 `dwMethodFlags`  
 [in] Il valore di [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione che specifica gli attributi del metodo o della funzione globale.  
  
 `pvSigBlob`  
 [in] La firma del metodo. La firma viene mantenuta come fornito. Se è necessario specificare informazioni aggiuntive per i parametri, utilizzare il [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) metodo.  
  
 `cbSigBlob`  
 [in] Il numero di byte in `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] L'indirizzo del codice.  
  
 `dwImplFlags`  
 [in] Il valore di [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica le funzionalità di implementazione del metodo.  
  
 `pmd`  
 [out] Il token di membro.  
  
## <a name="remarks"></a>Note  
 L'API dei metadati garantisce che vengano mantenuti metodi nello stesso ordine in cui il chiamante vengono generati per una determinata classe o un'interfaccia, specificata nel `td` parametro.  
  
 Informazioni aggiuntive relative all'uso di `DefineMethod` e impostazioni particolari dei parametri sono specificati di seguito.  
  
## <a name="slots-in-the-v-table"></a>Slot nella tabella V-table.  
 Il runtime utilizza le definizioni di metodo per impostare gli slot v-table. Nel caso in cui devono essere ignorate, ad esempio uno o più slot per mantenere la parità con un layout di interfaccia COM, viene definito un metodo fittizio in modo da occupare lo slot o slot nella tabella v. impostare il `dwMethodFlags` per il `mdRTSpecialName` valore il [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumerazione e specificare il nome come:  
  
 VtblGap\<*SequenceNumber*>\<\_*NumeroDiSlot*>  
  
 dove *SequenceNumber* è il numero di sequenza del metodo e *NumeroDiSlot* è il numero di slot da ignorare nella v-table. Se *NumeroDiSlot* viene omesso, viene utilizzato il valore 1. Questi metodi fittizi non richiamabili da codice gestito o non gestito e qualsiasi tentativo di chiamarle da codice gestito o non gestito, genera un'eccezione. Il solo scopo è occupare spazio nella tabella v generati dal runtime per l'integrazione con COM.  
  
## <a name="duplicate-methods"></a>Metodi duplicati  
 Non è necessario definire metodi duplicati. Ovvero, non è necessario chiamare `DefineMethod` con un set di valori duplicati di `td`, `wzName`, e `pvSig` parametri. (Questi tre parametri insieme definiscono in modo univoco il metodo.). Tuttavia, è possibile utilizzare un duplicata condizione che, per una delle definizioni di metodo, è impostato il `mdPrivateScope` bit il `dwMethodFlags` parametro. (Il `mdPrivateScope` bit significa che il compilatore non genererà un riferimento a questa definizione di metodo.)  
  
## <a name="method-implementation-information"></a>Informazioni sul metodo di implementazione  
 Informazioni sull'implementazione del metodo spesso non sono noto al momento che il metodo viene dichiarato. Pertanto, non è necessario passare valori di `ulCodeRVA` e `dwImplFlags` parametri quando si chiama `DefineMethod`. I valori possono essere forniti in un secondo momento tramite [SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), a seconda dei casi.  
  
 In alcune situazioni, ad esempio la chiamata di platform (invoke PInvoke) o scenari di interoperabilità COM, non verrà fornito il corpo del metodo, e `ulCodeRVA` deve essere impostato su zero. In questi casi, il metodo non deve essere contrassegnato come abstract, perché il runtime consente di trovare l'implementazione.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definizione di un metodo per PInvoke  
 Per ogni funzione non gestita a essere chiamati tramite PInvoke, è necessario definire un metodo gestito che rappresenta la funzione non gestita di destinazione. Per definire il metodo gestito, utilizzare `DefineMethod` con alcuni parametri impostati su determinati valori, a seconda della modalità in cui viene utilizzato PInvoke:  
  
-   True PInvoke: comporta la chiamata di un metodo esterno non gestito che si trova in una DLL non gestita.  
  
-   PInvoke locale - comporta la chiamata di un metodo nativo non gestito che è incorporato nel modulo gestito di corrente.  
  
 Le impostazioni dei parametri sono indicate nella tabella riportata di seguito.  
  
|Parametro|Valori per PInvoke true|Valori per PInvoke locale|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Impostare `mdStatic`; deselezionare `mdSynchronized` e `mdAbstract`.|  
|`pvSigBlob`|Una firma del metodo di common language runtime (CLR) valido con i parametri validi di tipi gestiti.|Una firma del metodo CLR valida con i parametri validi di tipi gestiti.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Impostare `miCil` e `miManaged`.|Impostare `miNative` e `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
