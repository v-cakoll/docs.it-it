---
title: Metodo IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 7e60dd9535809ca13f3bbe6ac76f5ea1209df734
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501172"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="eb3d3-102">Metodo IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="eb3d3-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="eb3d3-103">Ottiene il nome, le dimensioni della riga, il numero di righe, il numero di colonne e l'indice della colonna chiave della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb3d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb3d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb3d3-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="eb3d3-106">in Identificatore della tabella le cui proprietà devono essere restituite.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="eb3d3-107">out Puntatore alla dimensione, in byte, di una riga di tabella.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="eb3d3-108">out Puntatore al numero di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="eb3d3-109">out Puntatore al numero di colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="eb3d3-110">out Puntatore all'indice della colonna chiave oppure-1 se la tabella non contiene colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="eb3d3-111">out Puntatore a un puntatore al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="eb3d3-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb3d3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb3d3-112">Requirements</span></span>  
 <span data-ttu-id="eb3d3-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb3d3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb3d3-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eb3d3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb3d3-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb3d3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb3d3-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb3d3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3d3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb3d3-117">See also</span></span>

- [<span data-ttu-id="eb3d3-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="eb3d3-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="eb3d3-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="eb3d3-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
