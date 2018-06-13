---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484188"
---
# <a name="activitytransfer"></a><span data-ttu-id="5001c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="5001c-102">ActivityTransfer</span></span>
<span data-ttu-id="5001c-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="5001c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5001c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5001c-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5001c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5001c-105">Methods</span></span>  
 <span data-ttu-id="5001c-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="5001c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5001c-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5001c-107">Properties</span></span>  
 <span data-ttu-id="5001c-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="5001c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="5001c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="5001c-109">ActivityID</span></span>  
  
-   <span data-ttu-id="5001c-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="5001c-110">Data type: object</span></span>  
    <span data-ttu-id="5001c-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5001c-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="5001c-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="5001c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="5001c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="5001c-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="5001c-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="5001c-114">Data type: object</span></span>  
    <span data-ttu-id="5001c-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="5001c-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="5001c-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="5001c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5001c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5001c-117">Requirements</span></span>  
  
|<span data-ttu-id="5001c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="5001c-118">MOF</span></span>|<span data-ttu-id="5001c-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5001c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5001c-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="5001c-120">Namespace</span></span>|<span data-ttu-id="5001c-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5001c-121">Defined in root\ServiceModel.</span></span>|
