---
title: Metodo IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a4305b94d785a764671a2d73f43facefd0da0e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782378"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="e9018-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="e9018-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="e9018-103">Ottiene un puntatore al token di metadati per il <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.</span><span class="sxs-lookup"><span data-stu-id="e9018-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e9018-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9018-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9018-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9018-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="e9018-106">[in] Il token di metadati che rappresenta il metodo per restituire i token di classe e l'interfaccia per.</span><span class="sxs-lookup"><span data-stu-id="e9018-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="e9018-107">[out] Il token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="e9018-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="e9018-108">[out] Il token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="e9018-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="e9018-109">Note</span><span class="sxs-lookup"><span data-stu-id="e9018-109">Remarks</span></span>

 <span data-ttu-id="e9018-110">Ottenere il valore per `iImpl` chiamando il [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e9018-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="e9018-111">Ad esempio, si supponga che una classe ha un `mdTypeDef` token valore 0x02000007 e l'implementazione di tre interfacce i cui tipi sono token:</span><span class="sxs-lookup"><span data-stu-id="e9018-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="e9018-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="e9018-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="e9018-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="e9018-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="e9018-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="e9018-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="e9018-115">Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come:</span><span class="sxs-lookup"><span data-stu-id="e9018-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="e9018-116">Numero di riga</span><span class="sxs-lookup"><span data-stu-id="e9018-116">Row number</span></span> | <span data-ttu-id="e9018-117">Token di classe</span><span class="sxs-lookup"><span data-stu-id="e9018-117">Class token</span></span> | <span data-ttu-id="e9018-118">Token di interfaccia</span><span class="sxs-lookup"><span data-stu-id="e9018-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="e9018-119">4</span><span class="sxs-lookup"><span data-stu-id="e9018-119">4</span></span>          |             |                 |
| <span data-ttu-id="e9018-120">5</span><span class="sxs-lookup"><span data-stu-id="e9018-120">5</span></span>          | <span data-ttu-id="e9018-121">02000007</span><span class="sxs-lookup"><span data-stu-id="e9018-121">02000007</span></span>    | <span data-ttu-id="e9018-122">02000003</span><span class="sxs-lookup"><span data-stu-id="e9018-122">02000003</span></span>        |
| <span data-ttu-id="e9018-123">6</span><span class="sxs-lookup"><span data-stu-id="e9018-123">6</span></span>          | <span data-ttu-id="e9018-124">02000007</span><span class="sxs-lookup"><span data-stu-id="e9018-124">02000007</span></span>    | <span data-ttu-id="e9018-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="e9018-125">0100000A</span></span>        |
| <span data-ttu-id="e9018-126">7</span><span class="sxs-lookup"><span data-stu-id="e9018-126">7</span></span>          |             |                 |
| <span data-ttu-id="e9018-127">8</span><span class="sxs-lookup"><span data-stu-id="e9018-127">8</span></span>          | <span data-ttu-id="e9018-128">02000007</span><span class="sxs-lookup"><span data-stu-id="e9018-128">02000007</span></span>    | <span data-ttu-id="e9018-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="e9018-129">0200001C</span></span>        |

<span data-ttu-id="e9018-130">Tenere presente, il token è un valore a 4 byte:</span><span class="sxs-lookup"><span data-stu-id="e9018-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="e9018-131">I 3 byte meno significativi contenere il numero di riga o RID.</span><span class="sxs-lookup"><span data-stu-id="e9018-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="e9018-132">Il byte alto contiene il tipo di token – 0x09 per `mdtInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="e9018-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="e9018-133">`GetInterfaceImplProps` Restituisce le informazioni contenute nella riga il cui token è fornire la `iImpl` argomento.</span><span class="sxs-lookup"><span data-stu-id="e9018-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="e9018-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9018-134">Requirements</span></span>  
 <span data-ttu-id="e9018-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9018-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9018-136">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9018-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9018-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e9018-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9018-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9018-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9018-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9018-139">See also</span></span>

- [<span data-ttu-id="e9018-140">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e9018-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e9018-141">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e9018-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
