---
title: Metodo IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: a031cdb875b5eb046428d4d235d3093caddb7a6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491290"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="ee945-102">Metodo IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="ee945-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="ee945-103">Ottiene un puntatore al tipo nativo non gestito del campo rappresentato dal token di metadati del campo specificato.</span><span class="sxs-lookup"><span data-stu-id="ee945-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee945-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee945-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee945-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee945-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ee945-106">in Token di metadati che rappresenta il campo per il quale ottenere le informazioni di marshalling di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="ee945-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="ee945-107">out Puntatore alla firma dei metadati del tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="ee945-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="ee945-108">out Dimensioni in byte di `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="ee945-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee945-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee945-109">Requirements</span></span>  
 <span data-ttu-id="ee945-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee945-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee945-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ee945-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee945-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee945-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee945-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee945-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee945-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee945-114">See also</span></span>

- [<span data-ttu-id="ee945-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ee945-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ee945-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ee945-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
