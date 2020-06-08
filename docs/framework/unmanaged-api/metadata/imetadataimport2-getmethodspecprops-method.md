---
title: Metodo IMetaDataImport2::GetMethodSpecProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 079d9245526ff7914d1cbd6a91f0f2d96a690af5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490445"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="96318-102">Metodo IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="96318-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="96318-103">Ottiene la firma dei metadati del metodo a cui fa riferimento il token MethodSpec specificato.</span><span class="sxs-lookup"><span data-stu-id="96318-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96318-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96318-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="96318-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96318-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="96318-106">in Token MethodSpec che rappresenta la creazione di un'istanza del metodo.</span><span class="sxs-lookup"><span data-stu-id="96318-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="96318-107">out Puntatore al token MethodDef o MethodRef che rappresenta la definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="96318-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="96318-108">out Puntatore alla firma dei metadati binari del metodo.</span><span class="sxs-lookup"><span data-stu-id="96318-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="96318-109">out Dimensione, in byte, di `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="96318-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96318-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96318-110">Requirements</span></span>  
 <span data-ttu-id="96318-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96318-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96318-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="96318-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="96318-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="96318-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="96318-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96318-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96318-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96318-115">See also</span></span>

- [<span data-ttu-id="96318-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="96318-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="96318-117">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="96318-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
