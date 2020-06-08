---
title: Metodo IMetaDataImport::FindTypeDefByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
ms.openlocfilehash: 5485f43afe08fafa559d0418327a8f4f186860e7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491511"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="73062-102">Metodo IMetaDataImport::FindTypeDefByName</span><span class="sxs-lookup"><span data-stu-id="73062-102">IMetaDataImport::FindTypeDefByName Method</span></span>
<span data-ttu-id="73062-103">Ottiene un puntatore al token di metadati TypeDef per l'oggetto <xref:System.Type> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="73062-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73062-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73062-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73062-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73062-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="73062-106">in Nome del tipo per il quale ottenere il token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="73062-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="73062-107">in Token TypeDef o TypeRef che rappresenta la classe contenitore.</span><span class="sxs-lookup"><span data-stu-id="73062-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="73062-108">Se il tipo da trovare non è una classe annidata, impostare questo valore su NULL.</span><span class="sxs-lookup"><span data-stu-id="73062-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="73062-109">out Puntatore al token TypeDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="73062-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73062-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73062-110">Requirements</span></span>  
 <span data-ttu-id="73062-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73062-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73062-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="73062-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73062-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="73062-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73062-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73062-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73062-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73062-115">See also</span></span>

- [<span data-ttu-id="73062-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="73062-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="73062-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="73062-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
