---
title: Metodo EmbedResource
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f6140e5f85a7ee21773c96a5abdccadaddab92e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777450"
---
# <a name="embedresource-method"></a>Metodo EmbedResource
Dichiara una risorsa incorporata. Questo metodo non incorpora effettivamente la risorsa.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly.  
  
 `FileToken`  
 Token file o ID assembly del file che contiene la risorsa.  
  
 `pszResourceName`  
 Nome della risorsa.  
  
 `dwOffset`  
 Offset della risorsa da RVA.  
  
 `dwFlags`  
 Flag di accessibilità `mrPublic` , `mrPrivate`ad esempio e. Questi flag possono essere passati al [Metodo DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
