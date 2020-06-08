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
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="b3142-102">Metodo IMetaDataImport::GetFieldProps</span><span class="sxs-lookup"><span data-stu-id="b3142-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="b3142-103">Ottiene i metadati associati al campo a cui fa riferimento il token FieldDef specificato.</span><span class="sxs-lookup"><span data-stu-id="b3142-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3142-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3142-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b3142-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3142-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b3142-106">in Token FieldDef che rappresenta il campo per il quale ottenere i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="b3142-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="b3142-107">out Puntatore a un token TypeDef che rappresenta il tipo della classe a cui appartiene il campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="b3142-108">out Nome del campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="b3142-109">in Dimensioni in caratteri wide del buffer per *szField*.</span><span class="sxs-lookup"><span data-stu-id="b3142-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="b3142-110">out Dimensioni effettive del buffer restituito.</span><span class="sxs-lookup"><span data-stu-id="b3142-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="b3142-111">out Flag associati ai metadati del campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="b3142-112">in Puntatore al valore dei metadati binari che descrive il campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="b3142-113">out Dimensioni in byte di `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="b3142-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="b3142-114">out Flag che specifica il tipo di valore del campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b3142-115">out Valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="b3142-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="b3142-116">out Dimensioni in caratteri di `ppValue` o zero se nessuna stringa esiste.</span><span class="sxs-lookup"><span data-stu-id="b3142-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3142-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3142-117">Requirements</span></span>  
 <span data-ttu-id="b3142-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3142-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3142-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3142-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3142-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b3142-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3142-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3142-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3142-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3142-122">See also</span></span>

- [<span data-ttu-id="b3142-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b3142-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b3142-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b3142-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
