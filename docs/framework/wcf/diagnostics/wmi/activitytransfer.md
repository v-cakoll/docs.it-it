---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034427"
---
# <a name="activitytransfer"></a><span data-ttu-id="7680b-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="7680b-102">ActivityTransfer</span></span>
<span data-ttu-id="7680b-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="7680b-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7680b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7680b-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7680b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7680b-105">Methods</span></span>  
 <span data-ttu-id="7680b-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="7680b-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7680b-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7680b-107">Properties</span></span>  
 <span data-ttu-id="7680b-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="7680b-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="7680b-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="7680b-109">ActivityID</span></span>  
  
-   <span data-ttu-id="7680b-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="7680b-110">Data type: object</span></span>  
    <span data-ttu-id="7680b-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7680b-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="7680b-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="7680b-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="7680b-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="7680b-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="7680b-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="7680b-114">Data type: object</span></span>  
    <span data-ttu-id="7680b-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="7680b-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="7680b-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="7680b-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7680b-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7680b-117">Requirements</span></span>  
  
|<span data-ttu-id="7680b-118">MOF</span><span class="sxs-lookup"><span data-stu-id="7680b-118">MOF</span></span>|<span data-ttu-id="7680b-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7680b-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7680b-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7680b-120">Namespace</span></span>|<span data-ttu-id="7680b-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="7680b-121">Defined in root\ServiceModel.</span></span>|
