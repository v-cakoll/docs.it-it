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
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177669"
---
# <a name="imetadataemitdefinemethod-method"></a>Metodo IMetaDataEmit::DefineMethod
Crea una definizione per un metodo o una funzione globale con la firma specificata e restituisce un token a tale definizione di metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Token `mdTypedef` della classe padre o dell'interfaccia padre del metodo. Impostare `mdTokenNil`su `td` , se si definisce una funzione globale.  
  
 `szName`  
 [in] Nome del membro in Unicode.  
  
 `dwMethodFlags`  
 [in] Valore dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) che specifica gli attributi del metodo o della funzione globale.  
  
 `pvSigBlob`  
 [in] Firma del metodo. La firma viene mantenuta come fornito. Se è necessario specificare informazioni aggiuntive per qualsiasi parametro, utilizzare il [metodo IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 [in] Numero di byte `pvSigBlob`in .  
  
 `ulCodeRVA`  
 [in] Indirizzo del codice.  
  
 `dwImplFlags`  
 [in] Valore dell'enumerazione [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) che specifica le funzionalità di implementazione del metodo.  
  
 `pmd`  
 [fuori] Token del membro.  
  
## <a name="remarks"></a>Osservazioni  
 L'API dei metadati garantisce la persistenza dei metodi nello stesso ordine in cui il `td` chiamante li genera per una determinata classe o interfaccia di inclusione, specificata nel parametro.  
  
 Ulteriori informazioni relative `DefineMethod` all'utilizzo e alle impostazioni dei parametri particolari sono riportate di seguito.  
  
## <a name="slots-in-the-v-table"></a>Slot nella tabella a V  
 Il runtime utilizza le definizioni di metodo per impostare gli slot v-table. Nel caso in cui uno o più slot devono essere saltati, ad esempio per mantenere la parità con un layout di interfaccia COM, viene definito un metodo fittizio per occupare lo slot o gli slot nella tabella v; impostare `dwMethodFlags` il `mdRTSpecialName` sul valore dell'enumerazione [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) e specificare il nome come:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 dove *NumeroSequenzo* è il numero di sequenza del metodo e *CountOfSlots* è il numero di slot da ignorare nella tabella v. Se *CountOfSlots* viene omesso, si presuppone 1. Questi metodi fittizi non sono chiamabili da codice gestito o non gestito e qualsiasi tentativo di chiamarli, da codice gestito o non gestito, genera un'eccezione. Il loro unico scopo è occupare spazio nella v-table che il runtime genera per l'integrazione COM.  
  
## <a name="duplicate-methods"></a>Metodi duplicati  
 Non è consigliabile definire metodi duplicati. Ovvero, non è `DefineMethod` necessario chiamare con un `td`set `wzName`duplicato di valori nei parametri , e `pvSig` . (Questi tre parametri insieme definiscono in modo univoco il metodo.). Tuttavia, è possibile utilizzare una tripla duplicata a `mdPrivateScope` condizione che, per una delle definizioni di metodo, si imposta il bit nel `dwMethodFlags` parametro. Il `mdPrivateScope` bit indica che il compilatore non genera un riferimento a questa definizione di metodo.  
  
## <a name="method-implementation-information"></a>Informazioni sull'implementazione del metodo  
 Le informazioni sull'implementazione del metodo spesso non sono note al momento della proprietà del metodo. Pertanto, non è necessario passare `ulCodeRVA` `dwImplFlags` valori nei `DefineMethod`parametri e quando si chiama . I valori possono essere forniti in un secondo momento tramite [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) o [IMetaDataEmit::SetRVA,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)in base alle esigenze.  
  
 In alcune situazioni, ad esempio la chiamata alla piattaforma (PInvoke) o gli `ulCodeRVA` scenari di interoperabilità COM, il corpo del metodo non verrà fornito e deve essere impostato su zero. In queste situazioni, il metodo non deve essere contrassegnato come astratto, perché il runtime individuerà l'implementazione.  
  
## <a name="defining-a-method-for-pinvoke"></a>Definizione di un metodo per PInvokeDefining a Method for PInvoke  
 Per ogni funzione non gestita da chiamare tramite PInvoke, è necessario definire un metodo gestito che rappresenta la funzione non gestita di destinazione. Per definire il metodo `DefineMethod` gestito, utilizzare con alcuni dei parametri impostati su determinati valori, a seconda del modo in cui viene utilizzato PInvoke:  
  
- True PInvoke- comporta la chiamata di un metodo non gestito esterno che risiede in una DLL non gestita.  
  
- PInvoke locale: comporta la chiamata di un metodo non gestito nativo incorporato nel modulo gestito corrente.  
  
 Le impostazioni dei parametri sono riportate nella tabella seguente.  
  
|Parametro|Valori per PInvoke true|Valori per PInvoke locale|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Imposta `mdStatic`; chiaro `mdSynchronized` `mdAbstract`e .|  
|`pvSigBlob`|Firma del metodo CLR (Common Language Runtime) valida con parametri di tipi gestiti validi.|Firma del metodo CLR valida con parametri di tipi gestiti validi.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Impostare `miCil` e `miManaged`.|Impostare `miNative` e `miUnmanaged`.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
