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
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777767"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="689bd-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="689bd-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="689bd-103">Ottiene un puntatore al token di metadati per il <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.</span><span class="sxs-lookup"><span data-stu-id="689bd-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="689bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="689bd-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="689bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="689bd-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="689bd-106">[in] Il token di metadati che rappresenta il metodo per restituire i token di classe e l'interfaccia per.</span><span class="sxs-lookup"><span data-stu-id="689bd-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="689bd-107">[out] Il token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="689bd-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="689bd-108">[out] Il token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="689bd-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="689bd-109">Note</span><span class="sxs-lookup"><span data-stu-id="689bd-109">Remarks</span></span>

 <span data-ttu-id="689bd-110">Ottenere il valore per `iImpl` chiamando il [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="689bd-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="689bd-111">Ad esempio, si supponga che una classe ha un `mdTypeDef` token valore 0x02000007 e l'implementazione di tre interfacce i cui tipi sono token:</span><span class="sxs-lookup"><span data-stu-id="689bd-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="689bd-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="689bd-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="689bd-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="689bd-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="689bd-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="689bd-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="689bd-115">Concettualmente, queste informazioni vengono archiviate in una tabella di implementazione dell'interfaccia come:</span><span class="sxs-lookup"><span data-stu-id="689bd-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="689bd-116">Numero di riga</span><span class="sxs-lookup"><span data-stu-id="689bd-116">Row number</span></span> | <span data-ttu-id="689bd-117">Token di classe</span><span class="sxs-lookup"><span data-stu-id="689bd-117">Class token</span></span> | <span data-ttu-id="689bd-118">Token di interfaccia</span><span class="sxs-lookup"><span data-stu-id="689bd-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="689bd-119">4</span><span class="sxs-lookup"><span data-stu-id="689bd-119">4</span></span>          |             |                 |
| <span data-ttu-id="689bd-120">5</span><span class="sxs-lookup"><span data-stu-id="689bd-120">5</span></span>          | <span data-ttu-id="689bd-121">02000007</span><span class="sxs-lookup"><span data-stu-id="689bd-121">02000007</span></span>    | <span data-ttu-id="689bd-122">02000003</span><span class="sxs-lookup"><span data-stu-id="689bd-122">02000003</span></span>        |
| <span data-ttu-id="689bd-123">6</span><span class="sxs-lookup"><span data-stu-id="689bd-123">6</span></span>          | <span data-ttu-id="689bd-124">02000007</span><span class="sxs-lookup"><span data-stu-id="689bd-124">02000007</span></span>    | <span data-ttu-id="689bd-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="689bd-125">0100000A</span></span>        |
| <span data-ttu-id="689bd-126">7</span><span class="sxs-lookup"><span data-stu-id="689bd-126">7</span></span>          |             |                 |
| <span data-ttu-id="689bd-127">8</span><span class="sxs-lookup"><span data-stu-id="689bd-127">8</span></span>          | <span data-ttu-id="689bd-128">02000007</span><span class="sxs-lookup"><span data-stu-id="689bd-128">02000007</span></span>    | <span data-ttu-id="689bd-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="689bd-129">0200001C</span></span>        |

<span data-ttu-id="689bd-130">Tenere presente, il token è un valore a 4 byte:</span><span class="sxs-lookup"><span data-stu-id="689bd-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="689bd-131">I 3 byte meno significativi contenere il numero di riga o RID.</span><span class="sxs-lookup"><span data-stu-id="689bd-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="689bd-132">Il byte alto contiene il tipo di token – 0x09 per `mdtInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="689bd-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="689bd-133">`GetInterfaceImplProps` Restituisce le informazioni contenute nella riga il cui token è fornire la `iImpl` argomento.</span><span class="sxs-lookup"><span data-stu-id="689bd-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="689bd-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="689bd-134">Requirements</span></span>  
 <span data-ttu-id="689bd-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="689bd-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="689bd-136">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="689bd-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="689bd-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="689bd-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="689bd-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="689bd-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689bd-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="689bd-139">See also</span></span>

- [<span data-ttu-id="689bd-140">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="689bd-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="689bd-141">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="689bd-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
