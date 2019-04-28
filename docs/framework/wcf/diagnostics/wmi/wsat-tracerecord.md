---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923409"
---
# <a name="wsattracerecord"></a><span data-ttu-id="efaa3-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="efaa3-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="efaa3-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="efaa3-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efaa3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efaa3-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="efaa3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="efaa3-105">Methods</span></span>  
 <span data-ttu-id="efaa3-106">La classe WSAT_TraceRecord non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="efaa3-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="efaa3-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="efaa3-107">Properties</span></span>  
 <span data-ttu-id="efaa3-108">La classe WSAT_TraceRecord dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="efaa3-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="efaa3-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="efaa3-109">ActivityID</span></span>  
 <span data-ttu-id="efaa3-110">Tipo di dati: oggetto</span><span class="sxs-lookup"><span data-stu-id="efaa3-110">Data type: object</span></span>  
<span data-ttu-id="efaa3-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="efaa3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efaa3-112">ID attività del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="efaa3-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="efaa3-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="efaa3-113">EventID</span></span>  
 <span data-ttu-id="efaa3-114">Tipo di dati: sint32</span><span class="sxs-lookup"><span data-stu-id="efaa3-114">Data type: sint32</span></span>  
<span data-ttu-id="efaa3-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="efaa3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efaa3-116">ID evento del record di traccia.</span><span class="sxs-lookup"><span data-stu-id="efaa3-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="efaa3-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="efaa3-117">TraceRecord</span></span>  
 <span data-ttu-id="efaa3-118">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="efaa3-118">Data type: string</span></span>  
<span data-ttu-id="efaa3-119">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="efaa3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="efaa3-120">Record di traccia</span><span class="sxs-lookup"><span data-stu-id="efaa3-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efaa3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efaa3-121">Requirements</span></span>  
  
|<span data-ttu-id="efaa3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="efaa3-122">MOF</span></span>|<span data-ttu-id="efaa3-123">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="efaa3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="efaa3-124">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="efaa3-124">Namespace</span></span>|<span data-ttu-id="efaa3-125">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="efaa3-125">Defined in root\ServiceModel</span></span>|
