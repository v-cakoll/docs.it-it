---
title: Metodo IMetaDataImport::GetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177241"
---
# <a name="imetadataimportgetfieldprops-method"></a>Metodo IMetaDataImport::GetFieldProps
Ottiene i metadati associati al campo a cui fa riferimento il token FieldDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mb`  
 [in] Token FieldDef che rappresenta il campo per cui ottenere i metadati associati.  
  
 `pClass`  
 [fuori] Puntatore a un token TypeDef che rappresenta il tipo della classe a cui appartiene il campo.  
  
 `szField`  
 [fuori] Nome del campo.  
  
 `cchField`  
 [in] Dimensione in caratteri di tipo "wide" del buffer per *szField*.  
  
 `pchField`  
 [fuori] Dimensione effettiva del buffer restituito.  
  
 `pdwAttr`  
 [fuori] Flag associati ai metadati del campo.  
  
 `ppvSigBlob`  
 [in] Puntatore al valore binario dei metadati che descrive il campo.  
  
 `pcbSigBlob`  
 [fuori] Dimensione in byte `ppvSigBlob`di .  
  
 `pdwCPlusTypeFlag`  
 [fuori] Flag che specifica il tipo di valore del campo.  
  
 `ppValue`  
 [fuori] Valore costante per il campo.  
  
 `pcchValue`  
 [fuori] Dimensione in caratteri `ppValue`di , o zero se non esiste alcuna stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
