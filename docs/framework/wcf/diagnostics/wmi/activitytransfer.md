---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964295"
---
# <a name="activitytransfer"></a><span data-ttu-id="a2cab-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="a2cab-102">ActivityTransfer</span></span>
<span data-ttu-id="a2cab-103">Evento trasferimento attività</span><span class="sxs-lookup"><span data-stu-id="a2cab-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2cab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2cab-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a2cab-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2cab-105">Methods</span></span>  
 <span data-ttu-id="a2cab-106">La classe ActivityTransfer non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="a2cab-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a2cab-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a2cab-107">Properties</span></span>  
 <span data-ttu-id="a2cab-108">La classe ActivityTransfer dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2cab-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a2cab-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="a2cab-109">ActivityID</span></span>  
  
- <span data-ttu-id="a2cab-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="a2cab-110">Data type: object</span></span>  
    <span data-ttu-id="a2cab-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2cab-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a2cab-112">ID attività</span><span class="sxs-lookup"><span data-stu-id="a2cab-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="a2cab-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="a2cab-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="a2cab-114">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="a2cab-114">Data type: object</span></span>  
    <span data-ttu-id="a2cab-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="a2cab-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a2cab-116">ID attività correlata</span><span class="sxs-lookup"><span data-stu-id="a2cab-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2cab-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2cab-117">Requirements</span></span>  
  
|<span data-ttu-id="a2cab-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a2cab-118">MOF</span></span>|<span data-ttu-id="a2cab-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a2cab-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a2cab-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a2cab-120">Namespace</span></span>|<span data-ttu-id="a2cab-121">Definito in root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a2cab-121">Defined in root\ServiceModel.</span></span>|
