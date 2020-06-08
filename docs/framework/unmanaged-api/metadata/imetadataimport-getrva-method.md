---
title: Metodo IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 58ab9ee9381fce4d7af1910df6c8d3bb813bcf13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490892"
---
# <a name="imetadataimportgetrva-method"></a>Metodo IMetaDataImport::GetRVA
Ottiene l'indirizzo RVA (relative Virtual Address) e i flag di implementazione del metodo o del campo rappresentato dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tk`  
 in Token di metadati MethodDef o FieldDef che rappresenta l'oggetto di codice per il quale restituire l'RVA. Se il token è un FieldDef, il campo deve essere una variabile globale.  
  
 `pulCodeRVA`  
 out Puntatore all'indirizzo virtuale relativo dell'oggetto di codice rappresentato dal token.  
  
 `pdwImplFlags`  
 out Puntatore ai flag di implementazione per il metodo. Questo valore è una maschera di maschera dall'enumerazione [CorMethodImpl](cormethodimpl-enumeration.md) . Il valore di `pdwImplFlags` è valido solo se `tk` è un token MethodDef.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
