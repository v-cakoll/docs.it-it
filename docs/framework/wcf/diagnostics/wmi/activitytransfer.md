---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662816"
---
# <a name="activitytransfer"></a><span data-ttu-id="fa58e-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="fa58e-102">ActivityTransfer</span></span>
<span data-ttu-id="fa58e-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="fa58e-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa58e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa58e-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fa58e-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fa58e-105">Methods</span></span>  
 <span data-ttu-id="fa58e-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="fa58e-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fa58e-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fa58e-107">Properties</span></span>  
 <span data-ttu-id="fa58e-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa58e-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="fa58e-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="fa58e-109">ActivityID</span></span>  
  
- <span data-ttu-id="fa58e-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="fa58e-110">Data type: object</span></span>  
    <span data-ttu-id="fa58e-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="fa58e-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="fa58e-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="fa58e-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="fa58e-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="fa58e-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="fa58e-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="fa58e-114">Data type: object</span></span>  
    <span data-ttu-id="fa58e-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="fa58e-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="fa58e-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="fa58e-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa58e-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa58e-117">Requirements</span></span>  
  
|<span data-ttu-id="fa58e-118">MOF</span><span class="sxs-lookup"><span data-stu-id="fa58e-118">MOF</span></span>|<span data-ttu-id="fa58e-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fa58e-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fa58e-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fa58e-120">Namespace</span></span>|<span data-ttu-id="fa58e-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fa58e-121">Defined in root\ServiceModel.</span></span>|
