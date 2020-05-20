---
title: Interfaccia ISymUnmanagedENCUpdate
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: aa4fe2185ead7edfa47d4194799c930193e04076
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614526"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="0d06a-102">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="0d06a-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="0d06a-103">Fornisce funzioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="0d06a-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d06a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0d06a-104">Methods</span></span>  
  
|<span data-ttu-id="0d06a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0d06a-105">Method</span></span>|<span data-ttu-id="0d06a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d06a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d06a-107">Metodo GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="0d06a-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="0d06a-108">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="0d06a-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="0d06a-109">Metodo GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="0d06a-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="0d06a-110">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="0d06a-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="0d06a-111">Metodo InitializeForEnc</span><span class="sxs-lookup"><span data-stu-id="0d06a-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="0d06a-112">Consente il calcolo dei limiti del metodo prima della prima chiamata al metodo [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d06a-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="0d06a-113">Metodo UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="0d06a-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="0d06a-114">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono state spostate in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="0d06a-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="0d06a-115">È consentito un Delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="0d06a-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="0d06a-116">Metodo UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="0d06a-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="0d06a-117">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso del database di programma (PDB), purché le informazioni sulla riga soddisfino i requisiti.</span><span class="sxs-lookup"><span data-stu-id="0d06a-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="0d06a-118">Le informazioni sulla riga corrette possono essere determinate con le informazioni sulla riga PDB precedenti e un Delta per tutte le righe nella funzione.</span><span class="sxs-lookup"><span data-stu-id="0d06a-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d06a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d06a-119">Requirements</span></span>  
 <span data-ttu-id="0d06a-120">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0d06a-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d06a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d06a-121">See also</span></span>

- [<span data-ttu-id="0d06a-122">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="0d06a-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
