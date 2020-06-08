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
ms.openlocfilehash: 2bd05b49c3d51ac13865997910c99cc0cd5ca2d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491246"
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
 in Token FieldDef che rappresenta il campo per il quale ottenere i metadati associati.  
  
 `pClass`  
 out Puntatore a un token TypeDef che rappresenta il tipo della classe a cui appartiene il campo.  
  
 `szField`  
 out Nome del campo.  
  
 `cchField`  
 in Dimensioni in caratteri wide del buffer per *szField*.  
  
 `pchField`  
 out Dimensioni effettive del buffer restituito.  
  
 `pdwAttr`  
 out Flag associati ai metadati del campo.  
  
 `ppvSigBlob`  
 in Puntatore al valore dei metadati binari che descrive il campo.  
  
 `pcbSigBlob`  
 out Dimensioni in byte di `ppvSigBlob` .  
  
 `pdwCPlusTypeFlag`  
 out Flag che specifica il tipo di valore del campo.  
  
 `ppValue`  
 out Valore costante per il campo.  
  
 `pcchValue`  
 out Dimensioni in caratteri di `ppValue` o zero se nessuna stringa esiste.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
