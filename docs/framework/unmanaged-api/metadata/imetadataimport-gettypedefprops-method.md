---
title: Metodo IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490796"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="c21d0-102">Metodo IMetaDataImport::GetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="c21d0-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="c21d0-103">Restituisce le informazioni sui metadati per l'oggetto <xref:System.Type> rappresentato dal token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="c21d0-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c21d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c21d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c21d0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c21d0-106">in Token TypeDef che rappresenta il tipo per cui restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="c21d0-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="c21d0-107">out Buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="c21d0-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="c21d0-108">in Dimensioni in caratteri wide di `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="c21d0-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="c21d0-109">out Numero di caratteri wide restituiti in `szTypeDef` .</span><span class="sxs-lookup"><span data-stu-id="c21d0-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="c21d0-110">out Puntatore a tutti i flag che modificano la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="c21d0-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="c21d0-111">Questo valore è una maschera di maschera dall'enumerazione [CorTypeAttr](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c21d0-111">This value is a bitmask from the [CorTypeAttr](cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="c21d0-112">out Token di metadati TypeDef o TypeRef che rappresenta il tipo di base del tipo richiesto.</span><span class="sxs-lookup"><span data-stu-id="c21d0-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21d0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c21d0-113">Requirements</span></span>  
 <span data-ttu-id="c21d0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c21d0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21d0-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c21d0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c21d0-116">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c21d0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c21d0-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21d0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21d0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c21d0-118">See also</span></span>

- [<span data-ttu-id="c21d0-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c21d0-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c21d0-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c21d0-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
